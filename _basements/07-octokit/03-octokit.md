---
slide: 07-octokit
---

{:.text-white}
### Octokit y JavaScript

{:.fragment}
<pre><code data-line-numbers="3|10-23|25">
async function collectResults(studentUsername, totalLabs) {
  // https://github.com/booleancl/lab-19-DiegoMoralesC/actions/workflows/classroom.yml/badge.svg
  // https://docs.github.com/en/rest/reference/actions#list-jobs-for-a-workflow-run
  const studentLabsRequesPaths = getStudentLabsRequestPaths(
    studentUsername,
    totalLabs
  )
  const results = []
  
  for (labRequest of studentLabsRequesPaths) {
    console.log(`Processing ${labRequest.labPath} for student ${studentUsername}`)

    try {
      const workflowsResponse = await octokit.request(labRequest.url)
      const [ lastWorkflow ] = workflowsResponse.data.workflow_runs
      
      if (!lastWorkflow) {
        const message = `Lab ${labRequest.labPath} without Autograding`
        results.push({
          id: labRequest.labPath,
          status: 'completed',
          conclusion: 'success-with-failure',
          message
        })
        continue
      }

      const jobsResponse = await octokit.request(`GET /repos/booleancl/${labRequest.labPath}/actions/runs/${lastWorkflow.id}/jobs`)
      const [ lastPipeline ] = jobsResponse.data.jobs
        .map(({ status, conclusion, html_url}) => ({
          id: labRequest.labPath,
          status,
          conclusion,
          html_url,
          message: `Lab ${labRequest.labPath} ${conclusion === 'success'? 'OK' : 'FAILED'}`
        }))

      results.push(lastPipeline)
    } catch (error) {
      results.push({
        id: labRequest.labPath,
        status: 'failure',
        conclusion: 'failure',
        message: `Lab ${labRequest.labPath} FAILED: ${error.message}` 
      })
    }
    clearLastLine()
  }

  return Promise.resolve(results)
}

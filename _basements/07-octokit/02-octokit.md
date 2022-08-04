---
slide: 07-octokit
---

{:.text-white}
### Octokit y JavaScript

{:.fragment}
<pre><code data-line-numbers="3|5-14|15">
async function checkStudentLaboratoriesResults(studentUsername, totalLabs) {
  return collectResults(studentUsername, totalLabs)
    .then(results => {
      const { progressDisplay, progressValue } = getCourseCompletedPercentage(results, totalLabs)
      const studentResults = { 
        [studentUsername]: {
          username: studentUsername,
          lastRevision: (new Date()).getTime(),
          successTasks: progressDisplay,
          completedPercentage: progressValue,
          results
        }
      }
      return prettyCheckLabsMessage(studentUsername, studentResults)
    })
}

---
slide: 07-octokit
---

{:.text-white}
### Octokit y JavaScript

{:.fragment}
<pre><code data-line-numbers="5-11">
function getStudentLabsRequestPaths(studentUsername, totalLabs) {
  const labPaths = []

  for (let labIndex = 1; labIndex <= totalLabs; labIndex++) {
    const labId = labIndex < 10 ? `0${labIndex}` : labIndex
    const labPath =  `${PREFIX_LAB}-${labId}-${studentUsername}`
    const url =  `GET /repos/booleancl/${labPath}/actions/runs`

    labPaths.push({ labPath, url })
  }
  return labPaths
}
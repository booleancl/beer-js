---
slide: 07-octokit
---

{:.text-white}
### Octokit y JavaScript

{:.fragment}
<pre><code data-line-numbers="27|3-8|10-23|25">
async function main() {
  const studentsList = await getStudentsList()
  const laboratories = await getCourseLaboratories() || []
  const usernamesList = studentsList
    .map(({ username }) => username)

  let courseLabsResultsMap = {}
  // obtener resultados y obtener objeto, e imprimir objeto en cada iteración (privado)
  for (username of usernamesList) {
    try {
      const studentResults = await checkStudentLaboratoriesResults(username, laboratories.length)

      courseLabsResultsMap = {
        ...courseLabsResultsMap,
        ...studentResults,
      }
      await wait(3)
    } catch(error) {
      console.error(error)
      process.exit(1)
    }
  }

  await writeCourseLabsByStudent(courseLabsResultsMap)
}
main()
---
background: "/assets/img/base/SLIDES-COVER.jpg"
---

{:.text-white}
### Octokit y JavaScript

{:.fragment}
<pre><code data-line-numbers="3-5|6-7|8">
#!/usr/bin/env node
const {
  getStudentsList,
  getCourseLaboratories,
  writeCourseLabsByStudent,
  checkStudentLaboratoriesResults,
  wait
} = require('../src/main')



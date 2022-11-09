# Sonatype Deeper Data Workarounds


## Execute remediation of vulnerability using manifest version changes
- View version remediation and changing the version number
- Changing transient version numbers in Java Maven: https://stackoverflow.com/questions/39715882/how-to-specify-transitive-dependencys-version-in-maven 


## Explore workaround, configuration, and version change remediation options
- express-jwt has workaround
- Add recommended workaround node_modules > express-jwt > lib > index.js
- cmd: “npm pack”
- Upload to NXRM hosted-remediated repo
- cmd: “ npm set registry http:// NXRM REPO URL ”
- Delete node_modules
- Delete the package-lock.json (if we don't do this it will compare the hash from the old component to the new one and see a discrepancy, giving us a “EINTEGRITY” error)
- cmd: “npm cache clean --force”
- cmd: “npm install”
- See the remediated component by looking at node_modules > express-jwt > lib > index.js

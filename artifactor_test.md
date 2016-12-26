setup oss artifactory

https://www.jfrog.com/confluence/display/RTF/Running+Artifactory+OSS



  ```
curl -uadmin:xxxxxx -T /Users/guo/spm_push/test1-201506-2.spm  "http://localhost:8081/artifactory/salt-states/tkggo/test1-201506-2.spm"
{
  "repo" : "salt-states",
  "path" : "/tkggo/test1-201506-2.spm",
  "created" : "2016-12-26T13:21:48.595Z",
  "createdBy" : "admin",
  "downloadUri" : "http://localhost:8081/artifactory/salt-states/tkggo/test1-201506-2.spm",
  "mimeType" : "application/octet-stream",
  "size" : "383",
  "checksums" : {
    "sha1" : "f8a660d387f9036bc21b0bfb8d5254b5bc5bd5e5",
    "md5" : "5bac9b0b139ef3a95ec2102d756fefe1"
  },
  "originalChecksums" : {
  },
  "uri" : "http://localhost:8081/artifactory/salt-states/tkggo/test1-201506-2.spm"
  ```
  ```  ```
 curl -uadmin:xxxxxxx -O "http://localhost:8081/artifactory/salt-states/tkggo/test1-201506-2.spm"
  ```

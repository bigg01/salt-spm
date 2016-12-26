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



![arti](arti-test.jpeg)
```sudo salt-call state.show_sls arti
[WARNING ] /usr/lib/python2.7/site-packages/salt/grains/core.py:1493: DeprecationWarning: The "osmajorrelease" will be a type of an integer.

local:
    ----------
    test2-201506-2.spm:
        ----------
        __env__:
            base
        __sls__:
            arti
        file:
            |_
              ----------
              name:
                  /tmp/test2-201506-2.spm
            |_
              ----------
              source:
                  http://10.0.0.204:8081/artifactory/salt-states/tkggo/test2-201506-2.spm
            - managed
            |_
              ----------
              order:
                  10000
$ sudo salt-call state.apply arti test=True


local:
----------
          ID: test2-201506-2.spm
    Function: file.managed
        Name: /tmp/test2-201506-2.spm
      Result: None
     Comment: The file /tmp/test2-201506-2.spm is set to be changed
     Started: 21:28:30.874243
    Duration: 30.388 ms
     Changes:

Summary for local
------------
Succeeded: 1 (unchanged=1)
Failed:    0
------------
Total states run:     1
Total run time:  30.388 ms
$ sudo salt-call state.apply arti test=True
$ cat arti.sls
test2-201506-2.spm:
  file.managed:
    - name: /tmp/test2-201506-2.spm
    - source: http://10.0.0.204:8081/artifactory/salt-states/tkggo/test2-201506-2.spm
    
    

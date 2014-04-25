# puppeet-aptly

####Table of Contents
1. [License](#license)
2. [Requirements](#requirements)
3. [Usage](#usage)

## License
```
                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/
```

## Requirements
* puppetlabs/apt

## Usage
### aptly
It only install upstream aptly repo into apt/sources.list.d/ and install aptly
it self.

`include aptly`

### aptly::conf
Configures aptly by creating /etc/aptly.conf file.
```
  class {'aptly::conf':
    rootdir       => '/mnt/aptly',
    server_port   => '80',
    architectures => ['i386','amd64']
  }
```
Parameters:

  rootdir - where all aptly created repo data is going to be storred

  server_port - port on which aptly server will listen (default is 82)

  architectures - what architectures aptly should support, default is amd64
    but there can be more, all which are supported by distro kernel

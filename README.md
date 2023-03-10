# DBStream

Streaming MSSQL database between instances. DBStream is based on DB Backup and Restore. It streams backup blocks in memory from source to target server where Restore runs in parallel. No need of disk space for backup files. 

## Similarity

The only similarity for now is Auto-seeding. DBStream is independent with tons of flexibility, while Auto-seeding is tightly coupled with Availability Group which introduces extra limiations such as MSSQL version, edition, WSFC, etc. 

## Download

| version | Windows                                                      | Linux                                                        |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.0.0    | [DBStream_1.0_Win.zip](https://gasql.com/media/DBStream_1.0_Win.zip) | [DBStream_1.0_Linux.zip](https://gasql.com/media/DBStream_1.0_Linux.zip) |

## Disclaimer

[gasql](https://gasql.com) & [gasql/DBStreamb](https://github.com/gasql/DBStream) are the only 2 officially maintained site for publishing information and new releases of DBStream.

Be aware when you download DBStream binaries from other sources.

## Features

* Support Windows & Linux(CentOS/REHL v7/8, etc.).
* Support SQL Server 2008 or above.
* Support instances in on-prem or cloud VM.

## Prerequisites

* Microsoft Visual C++ Redistributable for Visual Studio 2022 (x64)
* ODBC Driver v17 for SQL Server (x64)

## Permissions
### Windows
* Run DBStream as Administrator
* sysadmin permissions on MS SQL Server
### Linux 
* user of mssql

## Installation
No need to install. Just copy, paste & run

## Start Case

- Download DBStream to Server1(Source) and Server2(Target), then unzip to your preferred location. 

- Make sure (1) C++ runtime and ODBC are installed (2) SQL Server is installed (3) Current Windows/Domain Account has MSSQL sysadmin privileges. in both Server1 and Server2.

- Make sure Server1's IP is in Valide IP list (ValidIPs) of config.ini in Server2. Otherwise, Server2 will deny data packets from Server1.

- Open Windows Console as administrator, and run the following command in Server2. 

  [AppPath]> DBStream.exe -l=3306

- Open Windows Console as administrator, and run the following command in Server1. Then DBStream will stream TestDB database from Server1 to Server2.

  [AppPath]>DBStream.exe -d=TestDB -f="tcp://Server2:3306"

*3306 means, Server1 transfers data to Server2 by TCP-3306. So, make sure it's not blocked by firewall. Otherwise, change it to other available port.

## Syntax & Usage
https://gasql.com/dbstream/syntax.html

## More Info
https://gasql.com/dbstream/

## Contact Me

- Email: gasql@outlook.com

## Change Log

#### v10.0.0 (2022-12-31)

- Initial Release

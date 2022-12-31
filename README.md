# DBStream

Streaming MSSQL database between instances. No need of disk space for backup files. 

## Similarity

The only similarity for now is Auto-seeding. But Auto-seeding is not independent. It's hard to use auto-seeding out of AG creation case, while DBStream is easy and flexible.

## Download

| version | Windows                                                      | Linux                                                        |
| ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.0.0    | [DBStream_1.0_Win.zip](https://gasql.com/media/DBStream_1.0_Win.zip) | [DBStream_1.0_Linux.zip](https://gasql.com/media/DBStream_1.0_Linux.zip) |

## Disclaimer

[gasql](https://gasql.com) & [gasql/DBStreamb](https://github.com/gasql/DBStream) are the only 2 officially maintained site for publishing information and new releases of DBStream.

Be aware when you download DBStream binaries from other sources.

## Features

* Support Windows & Linux(CentOS/REHL v7/8, etc.).
* Support SQL Server 2008 ~ SQL Server 2022.
* Support instances in on-prem or cloud VM.

## Prerequisites

* Microsoft Visual C++ Redistributable for Visual Studio 2022 (x64)
* ODBC Driver v17 for SQL Server (x64)

## Permissions
### Windows
* Runs DBStream as Administrator
* sysadmin permissions on MS SQL Server
### Linux 
* user of mssql

## Installation
No need to install. Just copy, paste & run

## Start Case

- Download DBStream to Server1(Source) and Server2(Target), then unzip to your preferred location. 

- Make sure (1) C++ runtime and ODBC are installed (2) SQL Server is installed (3) Current Windows/Domain Account has MSSQL sysadmin privileges. in both Server1 and Server2.

- Open Windows Console as administrator, and run the following command in Server2. 

  [AppPath]> DBStream.exe -l=3306

- Open Windows Console as administrator, and run the following command in Server1. Then TestDB will stream from Server1 to Server2.

  [AppPath]>DBStream.exe -d=TestDB -f="tcp://Server2:3306"

*3306 means, Server1 transfers data to Server2 by TCP-3306. So, make sure it's not blocked by firewall. Otherwise, change it to other available port.

## Syntax & Usage
https://gasql.com/dbstream/syntax.html

## More Info
https://gasql.com/dbstream/

## Contact Me

- Email: gasql@outlook.com

## Change Log


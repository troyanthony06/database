# Install Oracle Autonomous Health Framework (AHF)

## Introduction

In this lab, you will learn how to install AHF either as **root** or as a non-root user. You will also learn how to run AHF on SELinux-enabled systems.

Estimated Time: 30 minutes

### Objectives

In this lab, you will:
* (Recommended) Generate an AHF Insights report
Copy this report into a local directory  for subsequebt browser access

### Prerequisites

* Oracle recommends installing AHF as the **root** user. For this workshop, run the **sudo su** command to gain **root** access.
* Perl version 5.10 or later installed.

## Task 1: Open a terminal window

1. Lauch remote desktop.
2. Click **Activities** at the upper-left corner, and then click the **Terminal** icon.

    >**Note:** When you log in to the terminal, you will be logging in as the **opc** user.



    ```
    sudo su - 
    ```

    Command output:
## Task 1: Verify AHF is running
    ```
    sudo su - 
    ```
    ```
    /opt/oracle.ahf/bin/ahfctl statusahf 
    ```

    Command output:
    Command output:
    <pre>
    -------------------------------------------------------------------------------------------.
| Host                 | Status of TFA | PID   | Port  | Version    | Build ID              |
+----------------------+---------------+-------+-------+------------+-----------------------+
| ll88415-instance-ahf | RUNNING       | 47230 | 23197 | 24.4.0.0.0 | 240400020240503050950 |
'----------------------+---------------+-------+-------+------------+-----------------------'

    Extracting AHF to /opt/oracle.ahf
    Configuring TFA Services
    Discovering Nodes and Oracle Resources
    Successfully generated certificates.
    Starting TFA Services
    Created symlink /etc/systemd/system/multi-user.target.wants/oracle-tfa.service → /etc/systemd/system/oracle-tfa.service.
    Created symlink /etc/systemd/system/graphical.target.wants/oracle-tfa.service → /etc/systemd/system/oracle-tfa.service.

    .------------------------------------------------------------------------------------------.
    | Host                 | Status of TFA | PID   | Port  | Version    | Build ID             |
    +----------------------+---------------+-------+-------+------------+----------------------+
    | ll46863-instance-ahf | RUNNING       | 14895 | 22303 | 22.1.0.0.0 | 22100020220529214423 |
    '----------------------+---------------+-------+-------+------------+----------------------'

    ```
**Note**: your **instance name** will be different to the one shown here.
The version should be *24.4.0



## Acknowledgements
* **Author** - Troy Anthony
* **Contributors** -  Sarahi Partida, Robert Pastijn, Girdhari Ghantiyala, Anuradha Chepuri
* **Last Updated By/Date** - Troy Anthony, JulyJune 2024-

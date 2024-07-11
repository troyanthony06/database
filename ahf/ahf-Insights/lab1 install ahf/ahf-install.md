# Install Oracle Autonomous Health Framework (AHF)

## Introduction

In this lab, you will learn how to install AHF either as **root** or as a non-root user. You will also learn how to run AHF on SELinux-enabled systems.

Estimated Time: 30 minutes

### Objectives

In this lab, you will:
* (Recommended) Install AHF on Linux or UNIX as **root** user in daemon mode


### Prerequisites

* Oracle recommends installing AHF as the **root** user. For this workshop, run the **sudo su** command to gain **root** access.
* Perl version 5.10 or later installed.

## Task 1: Open a terminal window

1. Lauch remote desktop.
2. Click **Activities** at the upper-left corner, and then click the **Terminal** icon.

    >**Note:** When you log in to the terminal, you will be logging in as the **opc** user.

## Task 2: Install AHF on Linux or UNIX as root user in daemon mode

To obtain the fullest capabilities of Oracle Autonomous Health Framework (AHF), install it as **root**.
Try to use the latestst version of AHF to ensure you get all of the described functionality.
To generate an Insights report you need at least AHF **v22.3**
AHF can be downloaded fromMyOracle Support(MOS) throughnote**2550798.1** or follow the shortlink http://bit.ly/oracleahf
**A modified version of AHF is needed frLiveLabs For simplicity we have placed the install file for AHF **v24.5** in the Object Store

If Oracle Autonomous Health Framework is already installed, then reinstalling performs an upgrade to the existing location.



1. Switch to **root** user.

    ```
    <copy>
    sudo su
    </copy>
    ```
2. Download the AHF 24.4 zip fileile rom the object store
  ```
    cd ~opc/Downloads
    wget https://objectstorage.us-ashburn-1.oraclecloud.com/p/dKFif3QSyzV-R1-fTsPuojrCK7x5S0qirEyjs1AVmFwxw2hTpZs5UzUkBFCxtY-y/n/c4u04/b/livelabsfiles/o/labfiles/ahf_setup
    Command output:

    ```
    Connecting to objectstorage.us-ashburn-1.oraclecloud.com (objectstorage.us-ashburn-1.oraclecloud.com)|134.70.24.1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 420233163 (401M) [application/zip]
Saving to: ‘AHF-LINUX_v24.4.0.zip.1’

      AHF-L   0%       0  --.-KB/s     AHF-LI  15%  64.01M   289MB/s    AHF-LIN  24%  98.10M   181MB/s   AHF-LINU  33% 133.16M   179MB/s  AHF-LINUX  40% 160.93M   149MB/s AHF-LINUX_  47% 192.01M   144MB/sAHF-LINUX_v  57% 231.24M   138MB/sHF-LINUX_v2  69% 277.10M   142MB/sF-LINUX_v24  73% 294.96M   133MB/s-LINUX_v24.  80% 323.76M   133MB/sLINUX_v24.4  91% 366.38M   139MB/sINUX_v24.4.  93% 375.85M   130MB/sNUX_v24.4.0  96% 386.82M   125MB/sAHF-LINUX_v 100% 400.76M   127MB/s    in 3.2s    

2024-06-11 06:02:24 (127 MB/s) - ‘AHF-LINUX_v24.4.0.zip.1’ saved [420233163/420233163]
    ```
2. As the**root** user run the *ahf_setup* file directly.

    ```
    <copy>
    sudo su -
    cd  /home/opc/Downloads/
    ./ahf_setup
    </copy>
    ```
    Command output:


3. Run the **ahf_setup** script.

    ```
   
    ```

    Command output:

    <pre>
   AHF Installer for Platform Linux Architecture x86_64

AHF Installation Log : /tmp/ahf_install_244000_44824_2024_06_11-04_14_42.log

Starting Autonomous Health Framework (AHF) Installation

AHF Version: 24.4.0 Build Date: 202405030509

Default AHF Location : /opt/oracle.ahf

Do you want to install AHF at [/opt/oracle.ahf] ? [Y]|N : Y

Do you want to install AHF at [/opt/oracle.ahf] ? [Y]|N : Y
Please Enter AHF Data Directory : /opt/oracle.ahf/data

AHF Data Directory : /opt/oracle.ahf/data

Do you want to add AHF Notification Email IDs ? [Y]|N : N

Extracting AHF to /opt/oracle.ahf

Setting up AHF CLI and SDK

Configuring TFA Services

Discovering Nodes and Oracle Resources

Successfully generated certificates.

Starting TFA Services
Created symlink /etc/systemd/system/multi-user.target.wants/oracle-tfa.service -> /etc/systemd/system/oracle-tfa.service.
Created symlink /etc/systemd/system/graphical.target.wants/oracle-tfa.service -> /etc/systemd/system/oracle-tfa.service.

.-------------------------------------------------------------------------------------------.
| Host                 | Status of TFA | PID   | Port  | Version    | Build ID              |
+----------------------+---------------+-------+-------+------------+-----------------------+
| ll88415-instance-ahf | RUNNING       | 47230 | 23197 | 24.4.0.0.0 | 240400020240503050950 |
'----------------------+---------------+-------+-------+------------+-----------------------'

Running TFA Inventory...

Adding default users to TFA Access list...

.------------------------------------------------------------------.
|                   Summary of AHF Configuration                   |
+-----------------+------------------------------------------------+
| Parameter       | Value                                          |
+-----------------+------------------------------------------------+
| AHF Location    | /opt/oracle.ahf                                |
| TFA Location    | /opt/oracle.ahf/tfa                            |
| Orachk Location | /opt/oracle.ahf/orachk                         |
| Data Directory  | /opt/oracle.ahf/data                           |
| Repository      | /opt/oracle.ahf/data/repository                |
| Diag Directory  | /opt/oracle.ahf/data/ll88415-instance-ahf/diag |
'-----------------+------------------------------------------------'



1. Check the version of AHF installed.

    ```
    <copy>
    /opt/oracle.ahf/bin/tfactl print status
    </copy>
    ```

  	Command output:

    ```
    ..-------------------------------------------------------------------------------------------------------------.
| Host                 | Status of TFA | PID  | Port  | Version    | Build ID              | Inventory Status |
+----------------------+---------------+------+-------+------------+-----------------------+------------------+
| ll88415-instance-ahf | RUNNING       | 3616 | 29603 | 24.45.0.0.0 | 240400020240503050950 | COMPLETE         |
'----------------------+---------------+------+-------+------------+-----------------------+------------------'

    ```
**Note**: your **instance name** will be different to the one shown here.
The version should be *24.45.0
2. 
## Learn More

* [Installing and Upgrading Oracle Autonomous Health Framework](https://docs.oracle.com/en/engineered-systems/health-diagnostics/autonomous-health-framework/ahfug/install-upgrade-ahf.html#GUID-663F0836-A2A2-4EFB-B19E-EABF303739A9)
* [ahfctl setupgrade](https://docs.oracle.com/en/engineered-systems/health-diagnostics/autonomous-health-framework/ahfug/ahfctl-setupgrade.html#GUID-0AA4D7BE-781D-4345-BC77-A38AF10826BB)
* [ahfctl unsetupgrade](https://docs.oracle.com/en/engineered-systems/health-diagnostics/autonomous-health-framework/ahfug/ahfctl-unsetupgrade.html#GUID-7757592D-7E68-44EB-9ED0-14731146CFF6)
* [ahfctl getupgrade](https://docs.oracle.com/en/engineered-systems/health-diagnostics/autonomous-health-framework/ahfug/ahfctl-getupgrade.html#GUID-436F6822-FA11-4BE7-B28A-B8F0D9C01F97)
* [ahfctl upgrade](https://docs.oracle.com/en/engineered-systems/health-diagnostics/autonomous-health-framework/ahfug/ahfctl-upgrade.html#GUID-7EB170D6-DC9F-4EE3-9DD8-B5374B856179)
* [Oracle Autonomous Health Framework Installation Command-Line Options](https://docs.oracle.com/en/engineered-systems/health-diagnostics/autonomous-health-framework/ahfug/install-ahf.html#GUID-F57C15E1-B82A-42A1-B064-B6C86639799F)

## Acknowledgements
* **Author** - Troy Anthony
* **Contributors** -  Sarahi Partida, Robert Pastijn, Girdhari Ghantiyala, Anuradha Chepuri
* **Last Updated By/Date** - Trpy Anthony, June 2024

# Getting-started
prova pagina getting started dalla documentazione cineca a github

[UG2.1 Getting started](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.1+Getting+started)
==============================================================================================

-   Creato da [Neva Besker](https://wiki.u-gov.it/confluence/display/~n.besker@cineca.it), ultima modifica di [Antonio De Nicola](https://wiki.u-gov.it/confluence/display/~a.denicola@cineca.it) [ieri alle 4:26 PM](https://wiki.u-gov.it/confluence/pages/diffpagesbyversion.action?pageId=358197670&selectedPageVersions=35&selectedPageVersions=36 "Mostra le modifiche")

In the following, you can find a simple and quick **start guide** for users new to HPC systems and expert users who would like to use our systems.

It describes all the steps to be followed** to access our systems** up to the first job submission.

This is a schematic guide with a few examples, and it is not intended to be complete. We always strongly recommend **reading the full documentation** that can be reached using the links you can find along with the text.

* * * * *

The first step is to **get a username** on our database and a password to enter our HPC clusters.

1.  **Register** to our userDB database at [userdb.hpc.cineca.it](http://userdb.hpc.cineca.it/) by clicking on the "Create a New User" button and filling in the required fields.
2.  Once you get access, complete the info on your user page by uploading an **Identity Card** in the Documents for HPC tab, complete the information about your** Institution** and check your **Personal Data**.

This step alone does not grant you access to our clusters. You also need to be **associated with an account** that has budget resources with "cpu-hours" to be used in the clusters.

There are multiple ways to **get an account** budget (see also [UG2.2 Become a User](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.2%3A+Become+a+User)):

-   A **Principal Investigator** **(PI)** of an already existing account can add you to it in the [UserDB](http://userdb.hpc.cineca.it/) portal. Only the PI can add and remove collaborators to existing accounts;

-   You can apply for **your own project** by submitting your proposal for an [ISCRA](http://www.hpc.cineca.it/services/iscra) or [EuroHPC](https://prace-ri.eu/hpc-access/eurohpc-access/) projects;
-   If you are a member of an Italian research Institution with already existing **agreements** with CINECA (in this case, send an email to <superc@cineca.it>);
-   General users and **Industrial** **Applications** (send a request to <superc@cineca.it>)

Once your username has been associated with an active account, you can **request access** to our HPC clusters by clicking on the button "Submit" on your HPC Access page. (The button appears **only** after you have been associated with an account).

![](https://wiki.u-gov.it/confluence/download/attachments/358197670/submituserdb.jpg?version=1&modificationDate=1636739610000&api=v2)

After we have granted you access, you will receive two emails: one with the username and another with the link to the page where you can configure the two-factor authentication (2FA) needed to access our clusters. You can follow the "[How to activate the 2FA and configure the OTP](https://wiki.u-gov.it/confluence/display/SCAIUS/How+to+activate+the+2FA+and+configure+the+OTP)" page with dedicated instructions on how to configure the 2FA. You will also have to install a smallstep client ("[How to install the smallstep client](https://wiki.u-gov.it/confluence/display/SCAIUS/How+to+install+the+smallstep+client)") on your personal PC to download a temporary certificated needed for the login. During 2FA configuration you will be also asked to set a password. Please you can find our policy about password definition at the [dedicated page](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.3%3A+Access+to+the+Systems#UG2.3:AccesstotheSystems-Policyforpassworddefinition).

**Important:** The link for the configuration of the 2FA has a **duration of only 24 hours**. After its expiration you need to write to <superc@cineca.it> to get a new valid link.

**Remember:** Login credentials are to be considered **strictly personal**, meaning that **NO SHARING** between members of the same working group is expected to happen. Every single user entitled with login credentials is to be considered personally **responsible** for any misuse that should take place.

* * * * *

Once you configured the 2FA, you can login to the cluster in which the budget account you are associated with is active, by:

-   open a terminal and download a temporary certificate [using the step command](https://wiki.u-gov.it/confluence/display/SCAIUS/Setup+client+step-cli%3A+Linux+and+Mac+users#Setupclientstepcli:LinuxandMacusers-Activationofthessh-agent);
-   connect to the cluster launching the command

> ssh <username>@login.<cluster>.[cineca.it](http://cineca.it/)

(Windows users can find [here](https://wiki.u-gov.it/confluence/display/SCAIUS/Setup+client+step-cli%3A+Windows+users#Setupclientstepcli:Windowsusers-Activationofthessh-agent) the instructions)\
At present the only method to login to our clusters is via 2FA authentication. Please write to <superc@cineca.it> if you find problems in configuring and using it.

Available clusters are **Galileo100**, **Marconi,** **and Leonardo **([UG3.0 System specific guides](https://wiki.u-gov.it/confluence/display/SCAIUS/UG3.0%3A+System+Specific+Guides)).

**Important:** You can login only to clusters where you have active budgets on it.

* * * * *

On the cluster, you can keep an eye on your **budget** of hours using the command:

> saldo -b

This lists all the accounts associated with your username on the current cluster, together with the "budget" and the consumed resources.\
Additional **info** on this very useful command and our **billing policy** can be found on the "[UG2.4 Accounting](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.4%3A+Accounting)" page.

One username can use multiple accounts, and one single account can be used by multiple usernames (and even on multiple platforms), all competing for the same budget.

Some software, environments and compilers are already installed on the clusters and are available as **modules** ([UG2.6 Production Environment](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.6%3A+Production+Environment)).\
They are divided into different **profiles** depending on the category of research. The command

> modmap

shows all the profiles, categories and modules that you can load.

To load a module type:

> module load <module_name>

If the module is inside a specific profile, you have to load the profile before the module:

> module load profile/<profile_name>

There are many **useful options** for the functions "modmap" and "module" that are described [here](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.6%3A+Production+Environment#UG2.6:ProductionEnvironment-The%22module%22command).

* * * * *

You can also **install your libraries and programs** on your local folder by yourself or using [python](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.6%3A+Production+Environment#UG2.6:ProductionEnvironment-Pythonandadditionalsoftware) environment or [spack](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.6%3A+Production+Environment#UG2.6:ProductionEnvironment-HowtoinstallyoursoftwarewithSpack) manager. Please write to <superc@cineca.it> for any questions or requests about modules and software installations.

Our HPC systems offer several options for **data storage**:

-   **$HOME**: to store programs and small light results
-   **$CINECA_SCRATCH**: where you can execute your programs
-   **$WORK**: An area visible to all the users associated with the same budget account
-   **$DRES**: An additional area to store your results if they are heavy. This space is not automatic. You need to request for it writing to <superc@cineca.it>

Important details and suggestions on how to use each space can be found on the "[UG2.5 Data Storage and Filesystem](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.5%3A+Data+storage+and+FileSystems)" page.

To monitor the occupancy of your space, you can use the "[cindata](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.5%3A+Data+storage+and+FileSystems#UG2.5:DatastorageandFileSystems-Monitoringtheoccupancy)" command.

* * * * *

Once you have your compiled program and prepared its input data, the last step is to **run** it on the cluster's compute nodes.

**Important:** the node you are logged in is a login node and **cannot be used** to execute parallel programs.\
Login nodes are not used for production therefore the execution of any command in the login nodes is **limited** up to 10 minutes.

For longer runs, you need to use the "**batch**" mode. On CINECA machines we use the [SLURM scheduler](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.6.1%3A+How+to+submit+the+job+-+Batch+Scheduler+SLURM).

A simple **batch script** to submit a job is the following

#!/bin/bash

#SBATCH --nodes=<nodes_no>           # number of nodes\
#SBATCH --ntasks-per-node=<tasks_no> # number of tasks per node\
#SBATCH --time=01:00:00              # time limits: here 1 hour\
#SBATCH --mem=<memory>GB             # total memory per node requested in GB (optional)\
#SBATCH --error=myJob.err            # standard error file\
#SBATCH --output=myJob.out           # standard output file\
#SBATCH --account=<account_no>       # account name\
#SBATCH --partition=<partition_name> # partition name\
#SBATCH --qos=<qos_name>             # quality of service (optional)

srun ./my_application

In the script we tell the scheduler the amount of **resources** needed (--nodes, --ntasks-per-node and --mem) on which **partition** (--partition and --qos) and which **budget** of hours to be used (--account). The session has a **walltime** (--time) and the **outputs** of the code are collected in myJob.out and myJob.err (--output and --error respectively).\
The partition and the resources **depend on the machine** you are considering. All you need to know to properly fill your batch script can be found in the "[UG3.0 System specific guide](https://wiki.u-gov.it/confluence/display/SCAIUS/UG3.0%3A+System+Specific+Guides)" page.

* * * * *

To submit the job to the scheduler type

> sbatch [opts] job_script

You can find a complete list of examples of job scripts [here](https://wiki.u-gov.it/confluence/display/SCAIUS/UG2.6.1%3A+How+to+submit+the+job+-+Batch+Scheduler+SLURM#UG2.6.1:Howtosubmitthejob-BatchSchedulerSLURM-Examples).

As an alternative you can submit an **interactive** **job** opening a terminal session directly in a compute node:

 > salloc --nodes=<nodes_no> --ntasks-per-node=<tasks_no> --account=<account_no> --partition=<partition_name>

in which you can execute your program with the same inputs as the batch job.\
Remember to **close the interactive job** with the command "exit" when you have finished, in order not to waste your account budget.

Congratulations! You have successfully executed your first job on our clusters.\
**Remind**: Going through our detailed documentation may help you optimize your programs on our clusters and save hours of your budget.

For any problem or question, please refer to our Help Desk writing to <superc@cineca.it>.

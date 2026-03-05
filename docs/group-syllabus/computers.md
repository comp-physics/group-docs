# Computers

## Georgia Tech

* GT PACE Phoenix
    * User guide [here](https://docs.pace.gatech.edu/phoenix_cluster/gettingstarted_phnx/)
    * Login via `ssh <GTusername>@login-phoenix-rh9.pace.gatech.edu` to get the RHEL9 nodes
    * Purpose: All-purpose campus resource of CPU and GPU jobs with a variety of hardware.
    * "Rules": Use the `embers` queue type to use idle nodes at zero cost.
    * To get access, let Spencer know, and he will fill out [this form](https://gatech.service-now.com/home?id=sc_cat_item&sys_id=61bc5e351b37f994a8622f4b234bcbf0).

* GT ICE
  * [Resources/User guide](https://gatech.service-now.com/home?id=kb_article_view&sysparm_article=KB0042095) (click `Available Resources`, e.g.)
     * This looks like ~40 V100s, 8 A100s, 4 A40s, 20 RTX6000s, and 4 MI210s.
  * May need to contact Spencer for access.
  * __Most GPU nodes sit idle__
     * On those nodes: `MaxNodes=UNLIMITED MaxTime=18:00:00`

* GT Rogues Gallery
    * User guide [here](https://gt-crnch-rg.readthedocs.io/en/main/)
    * Purpose: Use of brand-new, forward-looking, or weird hardware. At the time of writing, it includes an NV H100 server, GH200 nodes, AMD MI210 GPU server, Bluefield-2/3 SmartNICs, RISC-V and Arm CPUs, etc.
    * "Rules": There are few rules; just follow the guidelines in the documentation. There are no limitations on hardware access/node hours.
    * Get access via [this link](https://crnch-rg.cc.gatech.edu/request-rogues-gallery-access/)

* GT Wingtip-gpu3
    * User guide [here](https://github.gatech.edu/cse-computing/compute-resources/blob/main/docs/systems/wingtip-gpu.md)
    * Purpose: Small (but possibly very long) GPU jobs, hosts 5x NV A100-80GB PCIe at the moment
    * "Rules":  Be mindful of others' use of this machine as it does not have a scheduler.
    * Get access by emailing [Will Powell](mailto:will.powell@cc.gatech.edu), cc me.

## University Clusters

* ACCESS-CI computers
    * These are a set of university supercomputers listed [here](https://access-ci.org/resource-providers/). Each has its own user guide. At the time of writing, we have access to NCSA Delta (A100 GPUs), PSC Bridges2 (V100 GPUs), Purdue Anvil, and Texas A&M ACES (H100 GPUs), but we can change to others as needed. We primarily use NCSA Delta.
    * Purpose: All-purpose resources for CPU and GPU simulation.
    * "Rules": Be mindful of the available node hours. Queue times might be long.
    * Our account number:
       * `PHY240200` (ACCESS-CI Maximize, NCSA Delta only)
       * `PHY210084` (ACCESS-CI Accelerate; Bridges2, Delta, and so on)
    * Get access by
        * Creating an account [here](https://identity.access-ci.org/new-user.html)
        * Then, message Spencer on Slack with your username
   * On [NCSA Delta](https://docs.ncsa.illinois.edu/systems/delta/en/latest/)
      * The account name is `bdiy-delta-gpu` (ACCESS-CI Maximize) or `bbsc-delta-gpu` (ACCESS-CI Accelerate) for GPU resources
      * Replace `-gpu` with `-cpu` for CPU resources

## DOE Labs

* Oak Ridge National Lab OLCF: Frontier/Wombat/Andes/etc.
    * Purpose
        * Frontier: Very large-scale GPU simulation on AMD MI250X GPUs.
        * Wombat: Testbed for next-gen HPC platforms, including ARM nodes and soon next-generation NVIDIA nodes (GraceHopper).
        * Andes: For postprocessing
    * Our account number: `CFD154`
    * "Rules": Ask Spencer before running any jobs that use a very large number of node hours
    * Get access by
        * Create an account by following [these instructions](https://docs.olcf.ornl.gov/accounts/accounts_and_projects.html#applying-for-a-user-account)
        * The account/allocation number is `CFD154`.

* Sandia National Lab (SNL)
    * Purpose: Resources for DOE-sponsored/funded research projects are only available to those students working on these projects. You will only have access to non-restricted resources.
    * "Rules": Usually, there are not many rules aside from the very many that they will impute onto you as you acquire access to these machines.
    * Login process (Sandia National Lab-specific)
        * Onto the DaaS
            * VMware Horizon ([download online](https://customerconnect.vmware.com/en/downloads/info/slug/desktop_end_user_computing/vmware_horizon_clients/horizon_8))
            * URL: `daas.sandia.gov`
            * Passcode: `[PIN] + [your yubikey1timepassword]`
            * Password: `[kerberos pw]`
            * 3 options
                * badge update
                * conference room
                * daas <- open this one
            * Can complete training and do other things here, like look at your WebCARS to get `WC_ID` (which you need to submit jobs)
        * Onto a computer remotely
            * https://hpc.sandia.gov/access/ssh/
            * Can do the below with DaaS (using my example username, `[usrname]`)
                * `ssh [usrname]@srngate.sandia.gov`
                * Passcode: `[PIN] + [yubikey one time pw]`
                * Choose a computer: e.g., Skybridge, Attaway, Weaver, etc.
                * Press `1` - `ssh session`
                * Default user name (`[usrname]`)
                * Password is (usually) the Kerberos one
                * If it asks for token OTP (e.g., on Weaver) then this is `[PIN] + [yubikey1timepassword]`

 * LLNL Livermore Computing: Lassen, Tioga, etc.
    * Anyone working on a specific LLNL project can use [LLNL CZ](https://lc.llnl.gov/) (non-restricted) resources
    * Talk to Spencer about getting access to CZ (collaboration zone) if you are working on a LLNL project
    * "Rules": Usually not many rules aside from the very many that they will impute onto you as you acquire access to these machines.
    * Login process (Lawrence Livermore National Lab-specific)
        * Onto LC-idm
            * URL: `ic-idm.llnl.gov`
            * Passcode: `[PIN] + [rsa one time password]`
            * Can use to view user profile and request roles (ask for resources on specific machines)
        * Onto the LC
            * URL: `lc.llnl.gov`
            * Passcode: `[PIN] + [rsa one time password]`
            * Requires three logins to fully log in
            * Can be used to access collaboration tools such as Confluence and Gitlab, user documentation, and MyLC for alerts, machine status, and job status
        * Onto a computer remotely
            * Can do the below with ssh (using my example username, `[usrname]`, for a specific LLNL machine, `[llnlmachine]`)
                * `ssh [usrname]@[llnlmachine].llnl.gov`
                * Passcode: `[PIN] + [rsa one time password]`

## DOD Labs

* Department of Defense
    * Anyone working on a DOD project can use [DOD HPCMP](https://www.hpc.mil/) (non-restricted) resources
    * The process of getting permissions to the non-restricted systems is a bit tedious but usually worth it
    * See [here](https://centers.hpc.mil/) for information on the available supercomputers
        * In particular, it's useful to keep an eye on [upcoming systems](https://centers.hpc.mil/systems/hardware.html#upcoming)
        * Current unclassified systems are [here](https://centers.hpc.mil/systems/unclassified.html)
    * Talk to Spencer about getting access to a DOD machine if you are working on a DOD project
    * Subproject: `ONRDC51242690`, Group: `5124D690`, Project: `5124`
       * Site: `NAVY`
          * nautilus
          * narwhal
       * Site: `ERDC`
          * carpenter
    * [Docs available here](https://centers.hpc.mil/users/docs/index.html#general)

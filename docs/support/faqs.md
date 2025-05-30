# FAQs

## Access and authentication

- [The frontend I am trying to log on does not respond](../../support/faqs-content/frontend-does-not-respond)

- [I get "No Kerberos credentials found" error after submitting the script](../../support/faqs-content/no-kerb-credenials)

- [I cannot access storage directories despite being logged in on a frontend](../../support/faqs-content/no-access-to-storages)

## Computing

- [My running job is coming close to walltime, can I prolong it?](../../support/faqs-content/prolong-walltime)

- [I get "permission denied" when I try to clean up scratch directory](../../support/faqs-content/clean-scratch-perm-denied)

- [Is there any tool to help me setup syntactically correct `qsub` command?](../../support/faqs-content/qsub-assembler)

- [I get an error "^M: command not found" or "$'\r': command not found" after submitting a script](../../support/faqs-content/os-dependent-endlines)

- [qdel command does not delete a job](../../support/faqs-content/force-qdel)

- [What are the default parameters in qsub command?](../../support/faqs-content/qsub-default-parameters)

- [My job failed with something like "No space left on device / Input-output error".](../../support/faqs-content/no-space-left)

- [My job is approaching walltime, can I prolong it?](../../support/faqs-content/prolong-walltime)

- [I get "Cgroup memsw limit exceeded" error, how to fix it?](../../support/faqs-content/cgroup-memsw-limit-exceeded)

## Data

- [I accidentally deleted a file/directory on storage, can I retrieve it?](../../support/faqs-content/accident-deleted-file)

- [Are SCRATCHDIR directories backed up somewhere?](../../support/faqs-content/scratchdir-backup)

- [How reliable/strong is the is backup policy on storages?](../../support/faqs-content/storage-backup-policy)

- [Where should I keep my longterm data?](../../support/faqs-content/where-keep-data)

- [I need more space on storage(s), can I get it?](../../support/faqs-content/more-space-storage)

## Software

- [Where can I find list of all installed software?](../../support/faqs-content/list-all-sw)

- [There are several version of one software, which one shall I use?](../../support/faqs-content/sw-which-version)

- [I get "Disk quota exceeded" error during installation, how do I fix this?](../../support/faqs-content/disk-quota-install)

<!-- FAQs "v zaloze"

-[]()
- How can I sort through various GPU and select among them?
    - some point to GPU card selection
    - also how to set memory for GPU card

-[]()
- I need to work interactively, but my internet connection is faulty. Is there a way to secure the connection so that I can reconnect to the interactive job?
    - some howto for this usecase
    - `nohup` (+ others?) in Linux, ??? other OSs 

-[]()
- How can I check whether I use resources effectively?
    - some howto on used mem, CPUs
    - duration is obvious
    - if CPU usage is low, usually the calculation is not so paralle as it should be 

-[]()
- How to speed up a job apart from running it in parallel?
    - depends on what the bottleneck is
    - choose CPU speed (if the bottleneck is CPU)
    - choose fast scratch (if the bottleneck is IN/OUT operations)

-[]()
- If I use N CPUs, will the job run N-times faster?
    - in general, no
    - the job must be paralellized
    - link to howto on paralellized jobs

-[]()
- why is my job queing so long? 
    - troubleshooting queing problems, explain fairshare, choice of resources
    - what affects queing time

-[]()
- My account has expired, what to do
    - howto where to reapply

-[]()
- I live and work abroad, collaborate with Czech colleagues, can I get an account?
    - howto how to get account
    - does need to be sponsored account?

-[]()
- I am a short-time guest in Czech republic, can I get an account?
    - about sponsored accounts
    - other alternatives to full account

-[]()
- I want to change my login, is that possible?
    - dtto, no its not possible

-[]()
- I want to change my password
    - dtto, for changing password

-[]()
- I forgot my pasword, what to do
    - howto for users in case they forgot password

-[]()
- I cannot login, what to do  
    - how to troubleshoot login problems
    - what to check first, ssh -vvv etc.
    - check frontends, outages - is the particular frontend down?
    - also check for IP ban

-[]()
- Can I use MetaCentrum services for commercial research?
    - is it strict "no"?

-[]()
- I need to receive large volume of data from outside MetaCentrum
    - how to do this effectively

-[]()
- Do you automatically install new versions of currently installed software?
    - in some cases yes (major software)
    - in more marginal cases you better tell us

-[]()
- Can I install my own software
    - yes, to your home
    - link to howto

-[]()
- I need to install .deb package, but I cannot use `apt-get install` without root priviledges. Is there some workaround?
    - some howto what to do
    - do they have always write to support?

-->

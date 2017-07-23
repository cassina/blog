
3. Notes
 - ```gitlab-runner``` cmd should be used with ```sudo```, the service is installed from the gitlab-runner directory but is running as root.
 - See runner status ```sudo gitlab-runner status```.
 - Reload runner ```sudo gitlab-runner restart```.
 - Help cmd ```sudo gitlab-runner help```.
 - We created a gitlab-runner user and a home dir for it so we do not get confused with the ubuntu user. If you need to create a new file that will be used by the runner, do it with gitlab-runner user permissions and in its home directory.

1. Install CI Runner
 - Create a new virtual machine, currently we use AWS EC2. We recommend Debian or Ubuntu 16 distros.
 - Install php and all the necessary dependencies for building the Laravel project *TODO improve with docs links, create issue**.
 - Install ```php-xml php-mbstring php-70-curl```.
 - Install the gitlab ci runner package. Run the linux manual installation following [this instructions](https://docs.gitlab.com/runner/install/linux-manually.html) and gather the URL and Token from [here](https://gitlab.com/crowdfundermx/cfmx-l5/settings/ci_cd). To know which type of system run ```dpkg --print-architecture```
 - If you followed the instructions now you should have an active runner [here](https://gitlab.com/crowdfundermx/cfmx-l5/settings/ci_cd)., remember to register the runner. Run ```sudo gitlab-runner status``` to confirm it says ```active```.
 - Now you can push any commits and the runner will follow the ```.gitlab-ci.yml``` configurations.

2. Update CI Runner
 - Update for Linux installation following [the instructions at the end](https://docs.gitlab.com/runner/install/linux-manually.html).
 - Run ```sudo gitlab-runner status``` to confirm it says ```active``` and perform a test pipeline.

4. Links
 - [Register a runner](https://docs.gitlab.com/runner/register/index.html)
 - [Installation](https://docs.gitlab.com/runner/install/linux-manually.html)
 - [Settings for our runner](https://gitlab.com/crowdfundermx/cfmx-l5/settings/ci_cd)

5. Rules:
 - *TODO write the rules applied to our builds*

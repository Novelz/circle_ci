# circle_ci
Simple CircleCI configuration for FTP deployment from git push.

Using CircleCI and [git-ftp](https://github.com/git-ftp/git-ftp) we can set up an automatic system to deploy the last changes on our FTP space.
The current configuration handle 2 different environments using 2 different branches.

**Development**  
The branch to use is `deployment_dev` and it connects to a staging environment using the 3 env variables `demo_host`, `demo_user` and `demo_password`.
You can set up these variables in the CircleCI project tab.

**Production**  
The branch for production is `deployment_prod` with the variables `prod_host`, `prod_user` and `prod_password`.

Every time you push something in one of these branches the changed files are pushed directly to the relative environment.


**NB:** for the first upload you can use the CLI command of git-ftp or set up a one time use pipeline in CircleCI, I'm currently using the first option.

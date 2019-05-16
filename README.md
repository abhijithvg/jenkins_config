# Using Configuration file with Jenkins Pipeline

If you are getting some error like "Scripts not permitted to use method ..." on executing this script, that means you are running your scripts in a sandbox environment and your script will need some permissions and you have to give permissions.

For that, 

1. Go to Jenkins > Manage Jenkins > In-process Script Approval
2. Here click 'Approve' button to approve the request made by the pipeline script. 
3. Build the job and continue this process until all the permission errors go away. 
4. Finally your 'Signatures already approved' section will look something like this:

`method java.util.Properties getProperty java.lang.String

method java.util.Properties load java.io.InputStream

new java.io.File java.lang.String

new java.util.Properties

staticMethod org.codehaus.groovy.runtime.DefaultGroovyMethods newDataInputStream java.io.File`

5. Done

Now when you build the job, the variables from the configuration file will be loaded in the environment variable and you will be able to use it.

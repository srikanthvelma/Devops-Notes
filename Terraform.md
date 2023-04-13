* Terraform interview questions and answers [refer][https://k21academy.com/terraform-iac/terraform-interview-questions/]

* `1. where is Terraform used in devops`
```sh
 Terraform is used in CI/CD pipelines to create required infra to deploy the application into different environments
```
* `2. IAC`
* ` Infrastucture as code : We can create required infra from code which will be used to automate the ci/cd pipelines ex: terraform ,ARM template,cloud formation`
* `3. what is module in terraform`
```
1. A module is container of multiple resources, which can be reusable by anybody

2. Every Terraform configuration has at least one module, known as its root module, which consists of the resources defined in the .tf files in the main working directory.

3. A module can cal other modules which lets you include all child module's resources into configuration .

4. we can cal child modules by using source argument ,which is mandatory in module

5. here the input variables of child module becomes arguments for calling module

6. In module we can also use outputs,variables,meta-argurmnts like count,for_each,depends_on,providers
```
* `4. What steps should be followed for making an object of one module to be available for the other module at a high level?`
```
1. first we should declare a output variable in resource configuration
2. we have create a output variable in module A with value as  
```
* `5. What is State File Locking?`
```
terraform state file locking is mechanisam that prevents the operations on 
a specific state file from being performed by multiple users at a time .
that means at a time only one user can use that, 
if one user release the state file,then other can use
```
* `6. what is remote backend in terraform`
```
Terraform remote backend is feature of terraform , 
where we can store state data files in remote like s3 in aws ,storage account in azure .
this is also compatible with workspaces
```
* `7. What is a Tainted Resource?`
```
1. Tainted resources are those ,which can be destroyed and created 
upon the next apply command,even though there are no changes in 
configuration of that resource.

2. for example if we changed the userdata script in vm creation, 
normally if you run terrform apply ,it will show no changes, 
then you taint that resource and try apply agian ,
it will destroy and re create
```
*`8. Does terraform supports multi-provider deployemnts`
```
yes terraform supports multi provider deployments,
as it is not tied up to a specific infrastructure or cloud provider
```
* `9. Define resource graph`
```
A rsource graph is graphical representation of available resources . 
it shows the resources in the images with dependencies . a full tree will be shown 
```
* `10. how can you define depencies in terraform`
```
In terraform we can define dependencies in 2 ways

1. explicity dependency -- by using depends_on argument . 
here in this you can mention multiple resources. 
so by doing this target source will be create after that

```
* `11.What happens when multiple engineers start deploying infrastructure using the same state file?`
```
when multiple users are using same state file, 
Terraform has feature "state locking", 
which will give access to only one user. 
if that user releases the lock then only others can use
```
* `12.Which value of the TF_LOG variable provides the MOST verbose logging?`
```
Trace is most verbose logging ,
which will give the complete information of terraform run
```
* `13. Which command can be used to preview the terraform execution plan?`
```
'terraform plan' is the command to preview the execution plan.

1. first it will reads the current state of any existing remote objects 
to make sure the terraform state is up to date

2. compares the current configuration and previous state and 
note down the differences

3. it proposes set of change actions ,
if we apply make the remote objects matches to the configuration
```
* `14. What is the benefit of Terraform State?`
```
1. This state file keeps track of resources created 
by our configuration and maps them to real-world resources.

2. terraform gives the plan by reading this state file

3. multiple users can create same resources 
by using this state file in different workspaces
```
* `15.What is the benefit of using modules in terraform?`
```
1. we can save time and avoid costly errors by reusing this modules

2. other team members are also can be used
```
* `16. what is null resource`
```
1. A null resource implement the standard resource lifecycle, 
but it cannot create any infra

2. it can be used to trigger a particular resource to be changed without destroying, 
insted of that resource this null resource will deleted and created, 
and the required change will done in the trigger resource

3. ex: we will used to change configuration in server with destroy them
```
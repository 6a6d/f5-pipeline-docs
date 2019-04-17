Delete a Deployed Service...again
=================================

#. Before moving forward, were going to delete the existing tenant.  This service will get redeployed using the CI/CD pipeline.
#. Delete the existing tenant using the AS3 Container.
#. Verify that the proper tenant has been deleted.
#. Log into the GitLab service.
#. Open the **f5-pipeline** project.
#. Reusing your AS3 Container service definition, create a new file in the **deploy** folder using the built-in editor.
#. Commit the file to the repository.  This commit will trigger the CI/CD pipeline built into GitLab.
#. Click on the pipeline icon (upper right corner), and watch the deployment.
#. After the deployment completes successfully, check the BIG-IP and verify the service was created successfully.

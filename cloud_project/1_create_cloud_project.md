# Create a Cloud Project in the Google Cloud Platform
The Google Cloud Platform (GCP) allows you to bundle together various cloud resources and APIs on an as-needed basis. A collection of related cloud resources for a particular application is termed a `Cloud Project`.

Every cloud resource you utilize must be included in a Cloud Project.

The cloud resources that are used are charged based on the pricing and usage for those resources. The Cloud Project is connected to a Billing Account, which is where the services are billed.

When you used your coupon code from Google Cloud, you were given a Billing Account with a credit of $50. You must now create a Cloud Project and attach it to that Billing Account.

(gcp:cloud_project:createcloudproject)=
## Create a New Cloud Project
Visit the [Google Cloud Console](https://console.cloud.google.com). If you see an option to create a **New Project**, choose it. Otherwise, visit the project selector dropdown menu at the top of the screen and then choose **New Project**.

On the New Project form, do the following:

1. Provide a project name that *begins with a letter* and clearly specifies the course for which you are creating the project. Project names must be unique in GCP, so you may consider including your username. A good project name would be `cit41200-username-scratch`, where `username` is your own unique username.

2. Choose the billing account associated with this course.

3. Choose the organization, if available.

4. Choose `Students` if given an option in the **Location** field.

5. Click the **Create** button.

Once your project is created, you will see the New Project Dashboard.

```{note}
On the dashboard you will see the **Project info** panel. *Copy the Project ID* from this panel. You will use it to connect to your GCP project from the Cloud Shell terminal.
```
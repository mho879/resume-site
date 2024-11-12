##### Codepipeline steps and progression #####
### Assumes you have a webapp made and ready
### Using static website made with React

# 1. Create an S3 bucket for Static Website Hosting 
## Enable static website hosting in bucket properties
## Set appropriate bucket policy permissions to allow public read access

# 2. Create CodeBuild
## Link GitHub repo
## Select Lambda and choose a Node.js version compatible with our React app
## Create a buildspec.yml file or edit one on the web console
### buildspec file needs to run npm install during installation and npm run build during build phases

# 3. Create CodePipeline to automate CI/CD
## Select Github as source and choose repo & branch
## Enable webhook for real-time updates
## Add buildstage and link CodeBuild
## Add Deploy stage and choose S3 as deploy provider
## Select S3 Bucket Created in Step 1
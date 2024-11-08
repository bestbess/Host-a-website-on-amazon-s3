

# Project: Hosting a Static Website on Amazon S3

## Overview
This project demonstrates how to host a static website using **Amazon S3**. Amazon Simple Storage Service (S3) is a scalable storage service that allows you to store and serve static assets like HTML, CSS, JavaScript, images, and other files. This project utilizes S3 to host a simple, static website with public access.

## Project Objectives
- **Deploy** a static website on Amazon S3.
- **Configure** S3 bucket settings to make the website accessible to the public.
- **Set up bucket policies** to manage access permissions.
- **Enable static website hosting** features for a smooth user experience.

## Key AWS Services Used
- **Amazon S3** - For hosting website files and enabling public access.
- **Amazon Route 53** *(Optional)* - For custom domain configuration.

## Project Structure
```plaintext
website-project/
├── index.html         # Main landing page for the website
├── about.html         # Additional static page
├── styles.css         # CSS for styling the pages
├── script.js          # JavaScript for interactive features
└── assets/            # Folder for images and other assets





Steps to Deploy the Static Website on Amazon S3
Step 1: Create an S3 Bucket

    Go to the S3 console in the AWS Management Console.
    Click on Create bucket.
    Bucket name: Choose a unique name (e.g., my-static-website-bucket).
    Region: Choose a preferred region.
    Uncheck Block all public access (required for static website hosting).
    Click Create bucket.

Step 2: Upload Website Files to the S3 Bucket

    Go to the newly created bucket and click on Upload.
    Upload the HTML, CSS, and JavaScript files, along with any other assets (like images).
    Organize files in folders if necessary, maintaining the structure shown above.

Step 3: Configure the Bucket for Static Website Hosting

    In the bucket settings, go to the Properties tab.
    Scroll down to Static website hosting and click Edit.
    Select Enable and set:
        Index document: index.html
        Error document: error.html (optional)
    Save the changes. An endpoint URL for the website will be generated.

Step 4: Set Up Bucket Policy for Public Access

    Go to the Permissions tab of the bucket.
    Click Bucket Policy and add a policy to allow public read access:
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-static-website-bucket/*"
    }
  ]
}



    Replace my-static-website-bucket with the name of your bucket.
    Save the policy to allow public access to your website files.

Step 5: Test the Website

    Copy the bucket website endpoint URL provided in the Static website hosting section.
    Paste the URL in your browser to view the website.
    Verify that the website loads as expected and all assets (like images and styles) are displayed correctly.

Step 6 (Optional): Configure a Custom Domain (Using Route 53)

If you own a custom domain and want to use it with your S3-hosted website, you can configure Amazon Route 53 to manage your domain and route it to your S3 bucket.
Project Outcome

The website is now accessible via the S3 bucket’s URL. This project demonstrates how S3 can be used to host static websites, showcasing AWS's capabilities for simple, low-cost website hosting without needing a traditional web server.
Key Takeaways

    Learned how to use Amazon S3 for static website hosting.
    Gained experience in configuring S3 bucket policies and permissions.
    Understood the basics of AWS's static website capabilities and custom domain routing with Route 53.

check out the screenshot for the final result in the root file.


Future Improvements

    Add HTTPS: Use Amazon CloudFront and an SSL certificate for secure HTTPS access.
    Custom Domain: Configure a custom domain and improve branding.



<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)

**Author:** agustinnico2302@gmail.com  
**Email:** agustinnico2302@gmail.com

---

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Introducing Today's Project!

### Project overview

In this project, I will host a website in a S3 bucket which is accessible in the public internet.

### Tools and concepts

The AWS service I used in this project is the Amazon S3, which taught me great concepts on deploying a static website without provisioning servers. I learned creating a bucket to prepare a space to put my files, configure Access Control List to disable blocking public access, upload website files to the bucket, and made them publicly accessible so it can be viewed via the public internet.

### Time, challenges, and wins

This project took me approximately 1-2 hours, since I was trying to understand the meaning behind the buttons of the console and reverse engineering the configuration to see different outcomes to understand features under this service more further.

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will create an S3 bucket in AWS Management Console.

### How long it took to create the bucket

Creating an S3 bucket took me for about 5-10 minutes because I'm figuring out the meaning behind the buttons of the S3 configuration.

### Region selection

The Region I picked for my S3 bucket was the ap-southeast-1, because it is the closest AWS region in which is beneficial to take advantage of low latency of accessing the applcation.

### Understanding bucket name uniqueness

S3 bucket names are globally unique. Since the bucket name is part of the website's URL, it must be unique so the URL is distinct from other websites around the world and as well as the bucket names of other AWS Accounts.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I will upload my websites' file or code to my newly created S3 bucket.

### Files I uploaded

I uploaded two files to my S3 bucket - they were the index.html and a folder that includes its dependencies like photos.

### How the files work together

Both files are necessary for this project as both are dependent with each other. In this case, index.html needs the photos inside of the folder to display them

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I will configure S3 bucket for static web hosting the files I uploaded can act as a working website.

### Understanding website hosting

Website hosting means storing a website’s files on a web server so people can access the website online.

### How I enabled website hosting

To enable website hosting for my S3 bucket, I opened the bucket’s Properties tab, scrolled to Static website hosting, enabled it, and specified `index.html` as the index document.

### Access Control Lists (ACLs)

An ACL is a set of rules that defines who can access resources in an S3 bucket. It can also grant access to other AWS accounts or make objects publicly accessible.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is called as the website endpoint URL. It is the web address for static website hosted in Amazon S3, its format depends on AWS Region it is deployed.

### What I saw when I tested the endpoint

When I first visited the bucket’s endpoint URL, I saw a “403 Forbidden” error. This happened because the objects in my bucket were private, so only the bucket owner had permission to access them. So to fix this, the objects must be publicly accessible.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_22ce4daf)

## Success!

### What I did in this step

For this step, I will make my objects or website files accessble in the public internet so anyone can access it.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I just selected all the checkboxes of the objects, clicked "Make Public using ACL" under actions. In this way, the objects can be accessible publicly (read only).

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension I'm about to set up a bucket policy that stops people from deleting objects in my S3 bucket. 

### Understanding bucket policies

An alternative to ACLs are bucket policies, which is a set of permissions that is attached to an S3 bucket, it uses JSON rules to specify who can access the bucket or objects, action they perform, if its allowed or denied, and the resources this policy apply. 

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_sm2sm2sm)

### What my bucket policy does

My bucket policy, it does not permit everyone to delete the index.html file. I tested this by deleting it by myself as the owner, however, it produces an error that says this action is denied. Which means that the bucket policy works.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)*

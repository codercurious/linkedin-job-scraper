## Getting Started
This scraper supports scraping 2 different versions of linkedin jobs search: 

### 1. Searching as an authenticated user 
In this version, linkedin supports most **advanced jobs searching features like boolean search, multiple filter values**, etc. You can also get additional info like skills. But to make use of that you need to **provide your linkedin cookies** to the scraper. Scraper will make sure your linkedin account is safe by using fixed proxy (you need to choose a proxy from your country) and random delays in between scraping pages, not using concurrency, etc. So the scraping will be slower with this version. 

### 2. Searching as a visitor
In this version, linkedin supports a **basic version of jobs search** which is **restricted to a few subset of features** supported by 1st version. To scrape jobs from this version of linkedin search, you don't have to provide cookies. It is **safer, supports proxy rotation, concurrency and faster scraping.**. 

Based on your requirements, you need to make a trade off between reliability and advanced features and decide which version of jobs search your want to scrape.

Scraper will decide which version of search page to scrape based on whether you have provided cookies or not. When cookies are provided, it will use advanced (version 1), otherwsie basic (version 2)

Go to [linkedin jobs search page](https://www.linkedin.com/jobs/search/), search with required filters and once you are done, copy the full URL from address bar and pass it to this actor. 

## How to get cookies 

Install [EditThisCookie](https://chrome.google.com/webstore/detail/editthiscookie/fngmhnnpilhplaeedifhccceomclgfbg) chrome extension 

Go to linkedin, and make sure you are logged in.

Click on the extension and export the cookies

Paste the cookies to this actor's `Cookie` input field

## Sample output data

You can get the output data in any format of your preference. 

Here is the sample output of this actor in json format: 


```json
{
	"id": "3692563200",
	"link": "https://www.linkedin.com/jobs/view/english-data-labeling-analyst-at-facebook-3692563200?refId=WG865nttvc0AIFSWNZZS8w%3D%3D&trackingId=wcG3vxpHJfGtFUkaaMVelQ%3D%3D&position=1&pageNum=0&trk=public_jobs_jserp-result_search-card",
	"title": "English Data Labeling Analyst",
	"companyName": "Facebook",
	"companyLinkedinUrl": "https://www.linkedin.com/company/facebook?trk=public_jobs_jserp-result_job-search-card-subtitle",
	"companyLogo": "https://media.licdn.com/dms/image/C4E0BAQHi-wrXiQcbxw/company-logo_100_100/0/1635988509026?e=2147483647&v=beta&t=pKAh1a653MsJvWqrqxSunoCVUALyq29eXX1oqobspnE",
	"location": "Los Angeles Metropolitan Area",
	"salaryInfo": [
		"$17.00",
		"$19.00"
	],
	"postedAt": "2023-08-16",
	"benefits": [
		"Actively Hiring"
	],
	"descriptionHtml": "<p>APPROVED REMOTE LOCATIONS:</p><p>Los Angeles, CA, San Fransisco Bay Area, CA, San Diego, CA, New York, NY, Denver, CO, Houston, TX, Seattle, WA.</p><p><br></p><p>Summary:</p><p>The main function of a data labeling analyst is to create and manage labeling and change processes within the data management systems. The typical data labeling analyst will have experience in data quality assurance.</p><p><br></p><p>Job Responsibilities:</p><p>• Create and modify data labels ensuring compliance to all regulatory and legal requirements.</p><p>• Maintain batch records, room logs, product travelers, and inventory records.</p><p>• Label and analyze large data sets to inform product decisions.</p><p>• Asses data quality.</p><p><br></p><p>Skills:</p><p>• Ability to identify trends within large data sets.</p><p>• Excellent communication skills, verbal and written.</p><p>• Problem solving skills.</p><p>• Team oriented with attention for detail.</p><p><br></p><p>Education/Experience:</p><ul><li>• Bachelors degree in related field.</li></ul>",
	"applicantsCount": "200",
	"applyUrl": "",
	"descriptionText": "APPROVED REMOTE LOCATIONS:Los Angeles, CA, San Fransisco Bay Area, CA, San Diego, CA, New York, NY, Denver, CO, Houston, TX, Seattle, WA.Summary:The main function of a data labeling analyst is to create and manage labeling and change processes within the data management systems. The typical data labeling analyst will have experience in data quality assurance.Job Responsibilities:• Create and modify data labels ensuring compliance to all regulatory and legal requirements.• Maintain batch records, room logs, product travelers, and inventory records.• Label and analyze large data sets to inform product decisions.• Asses data quality.Skills:• Ability to identify trends within large data sets.• Excellent communication skills, verbal and written.• Problem solving skills.• Team oriented with attention for detail.Education/Experience:• Bachelors degree in related field.",
	"jobPosterName": "Andrea Cowan",
	"jobPosterTitle": "Technical Recruiter at Meta",
	"jobPosterPhoto": "https://media.licdn.com/dms/image/C5603AQErv53vemaq_A/profile-displayphoto-shrink_100_100/0/1657753132661?e=1699488000&v=beta&t=5R1WgyX-TbL6qhhsntBeR5qmjKdTL5G2l2KtroVTntM",
	"jobPosterProfileUrl": "https://ca.linkedin.com/in/andrea-cowan-458b5423b",
	"seniorityLevel": "Associate",
	"employmentType": "Contract",
	"jobFunction": "Other",
	"industries": "Retail Office Equipment",
	"companyDescription": "The Facebook company is now Meta. Meta builds technologies that help people connect, find communities, and grow businesses. When Facebook launched in 2004, it changed the way people connect. Apps like Messenger, Instagram and WhatsApp further empowered billions around the world. Now, Meta is moving beyond 2D screens toward immersive experiences like augmented and virtual reality to help build the next evolution in social technology. \n\nWe want to give people the power to build community and bring the world closer together. To do that, we ask that you help create a safe and respectful online space. These community values encourage constructive conversations on this page:\n\n• Start with an open mind. Whether you agree or disagree, engage with empathy.\n• Comments violating our Community Standards will be removed or hidden. So please treat everybody with respect. \n• Keep it constructive. Use your interactions here to learn about and grow your understanding of others.\n• Our moderators are here to uphold these guidelines for the benefit of everyone, every day. \n• If you are seeking support for issues related to your Facebook account, please reference our Help Center (https://www.facebook.com/help) or Help Community (https://www.facebook.com/help/community).\n\nFor a full listing of our jobs, visit http://www.facebookcareers.com ",
	"companyWebsite": "https://www.meta.com",
	"companyEmployeesCount": 36275
}
```


If you want more details in scraped jobs like (Is Promoted?, Easy apply enabled?, Skills list), then you should pass your linkedin cookies. 

Here is the output data sample when scraped with cookies: 

```json
{
	"id": "3692563200",
	"title": "English Data Labeling Analyst",
	"companyName": "Facebook",
	"companyLinkedinUrl": "https://www.linkedin.com/company/facebook/life",
	"location": "Los Angeles Metropolitan Area (Remote)",
	"isReposted": false,
	"posterId": "1003153028",
	"companyLogo": "https://media.licdn.com/dms/image/C4E0BAQHi-wrXiQcbxw/company-logo_200_200/0/1635988509026?e=1701907200&v=beta&t=7TXR4pa66qrsBqzUaDJqQMyOSoshwoLp2Q7-_5R7lLw",
	"easyApply": true,
	"isPromoted": false,
	"descriptionText": "APPROVED REMOTE LOCATIONS:Los Angeles, CA, San Fransisco Bay Area, CA, San Diego, CA, New York, NY, Denver, CO, Houston, TX, Seattle, WA.\nSummary:The main function of a data labeling analyst is to create and manage labeling and change processes within the data management systems. The typical data labeling analyst will have experience in data quality assurance.\nJob Responsibilities:• Create and modify data labels ensuring compliance to all regulatory and legal requirements.• Maintain batch records, room logs, product travelers, and inventory records.• Label and analyze large data sets to inform product decisions.• Asses data quality.\nSkills:• Ability to identify trends within large data sets.• Excellent communication skills, verbal and written.• Problem solving skills.• Team oriented with attention for detail.\nEducation/Experience:• Bachelors degree in related field.",
	"applicantsCount": "853",
	"insights": [
		"$17/hr - $19/hr · Contract · Associate",
		"10,001+ employees · Software Development",
		"23 school alumni work here"
	],
	"applyUrl": "https://www.linkedin.com/job-apply/3692563200",
	"postedAtTimestamp": 1692217523000,
	"postedAt": "2023-08-16T20:25:23.000Z",
	"companyDescription": "The Facebook company is now Meta. Meta builds technologies that help people connect, find communities, and grow businesses. When Facebook launched in 2004, it changed the way people connect. Apps like Messenger, Instagram and WhatsApp further empowered billions around the world. Now, Meta is moving beyond 2D screens toward immersive experiences like augmented and virtual reality to help build the next evolution in social technology. \n\nWe want to give people the power to build community and bring the world closer together. To do that, we ask that you help create a safe and respectful online space. These community values encourage constructive conversations on this page:\n\n• Start with an open mind. Whether you agree or disagree, engage with empathy.\n• Comments violating our Community Standards will be removed or hidden. So please treat everybody with respect. \n• Keep it constructive. Use your interactions here to learn about and grow your understanding of others.\n• Our moderators are here to uphold these guidelines for the benefit of everyone, every day. \n• If you are seeking support for issues related to your Facebook account, please reference our Help Center (https://www.facebook.com/help) or Help Community (https://www.facebook.com/help/community).\n\nFor a full listing of our jobs, visit http://www.facebookcareers.com ",
	"companyWebsite": "https://www.meta.com",
	"companyEmployeesCount": 36275
}
```

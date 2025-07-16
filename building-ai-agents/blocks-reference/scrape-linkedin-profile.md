---
description: Get LinkedIn Profile Data
---

# Scrape LinkedIn Profile

The Scrape LinkedIn Profile block retrieves public information from a LinkedIn profile page. It is useful for enriching workflows with professional or organizational data such as job titles, company descriptions, locations, or industry tags.

This block requires a valid LinkedIn Profile URL and stores the response for downstream in the workflow.

***

## Configurations

### Profile URL

Enter the full URL of the LinkedIn profile or company page you want to scrape.

**Supported Formats:**

* Personal Profile: `https://linkedin.com/in/username`

> ⚠️ Only public profile data is available. Private or restricted content cannot be accessed.

***

### Output Variable

Specify the name of the variable where the scraped data should be stored. The result is typically returned as a JSON object.

**Example:** `linkedin_data`&#x20;

## Example Output

```json
{
  "fullName": "Dmitry Shapiro",
  "linkedin_internal_id": "3203",
  "first_name": "Dmitry",
  "last_name": "Shapiro",
  "public_identifier": "dmitry-shapiro-a2b1",
  "background_cover_image_url": "https://media.licdn.com/dms/image/v2/D5616AQEyFJsY9z6FPg/profile-displaybackgroundimage-shrink_200_800/profile-displaybackgroundimage-shrink_200_800/0/1707167096861?e=2147483647&v=beta&t=ZrJuQxSfNaPug6uf6_2CGumdQfl_v77pZmIy6LxOGIY",
  "profile_photo": "https://media.licdn.com/dms/image/v2/D5603AQHhQ4-UhGgpqA/profile-displayphoto-shrink_200_200/profile-displayphoto-shrink_200_200/0/1708916323677?e=2147483647&v=beta&t=pgJKywpBd1uCcVId7ZXTA6OPHGO3VEyQxS36iXc3iMw",
  "headline": "",
  "location": "San Diego County, California, United States",
  "followers": "30K followers",
  "connections": "500+ connections",
  "about": "",
  "experience": [
    {}
  ],
  "education": [],
  "articles": [
    {
      "link": "https://www.linkedin.com/pulse/world-models-jepa-next-evolution-ai-architecture-dmitry-shapiro-1xcsc",
      "image": "https://media.licdn.com/dms/image/v2/D5612AQHsxV3R2BAWYw/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1739115917775?e=2147483647&v=beta&t=ZHmxIvAX38zXu9p3clVJkrh6btoUJX94WxJ-iPeOtNY",
      "title": "World Models and JEPA: The Next Evolution in AI Architecture",
      "author": "",
      "published_date": "Feb 9, 2025"
    },
    {
      "link": "https://www.linkedin.com/pulse/qwen-25-alibabas-breakthrough-open-source-ai-dmitry-shapiro-8tepc",
      "image": "https://media.licdn.com/dms/image/v2/D5612AQGUy2CzCYkg0w/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1738161461626?e=2147483647&v=beta&t=D_JXXQhMwfRbN8yQfEMTR8wYDCPUcSO0SDGVY4kdLqk",
      "title": "Qwen-2.5: Alibaba's Breakthrough in Open-Source AI",
      "author": "",
      "published_date": "Jan 29, 2025"
    },
    {
      "link": "https://www.linkedin.com/pulse/deepseeks-openai-connection-unraveling-training-dmitry-shapiro-tdj3c",
      "image": "https://media.licdn.com/dms/image/v2/D5612AQFUOE0mb_JQAw/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1738123130175?e=2147483647&v=beta&t=1rI8TcN3dklkag2S8vJuzCzTEpz4iYhIaQfN-1EEVpg",
      "title": "DeepSeek's OpenAI Connection: Unraveling the Training Relationship",
      "author": "",
      "published_date": "Jan 29, 2025"
    },
    {
      "link": "https://www.linkedin.com/pulse/transforming-marketing-function-ai-automation-dmitry-shapiro-o6hcc",
      "image": "https://media.licdn.com/dms/image/v2/D5612AQHzGnV9th3CRQ/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1720672865633?e=2147483647&v=beta&t=UUqASUKVj_Q9Rar_F58GvMxZZEwh5nsgLFVly3FTVUY",
      "title": "Transforming the Marketing Function with AI Automation",
      "author": "",
      "published_date": "Jul 11, 2024"
    },
    {
      "link": "https://www.linkedin.com/pulse/most-sales-people-suck-can-we-get-them-perform-better-shapiro-5p4cc",
      "image": "https://media.licdn.com/dms/image/v2/D5612AQFovihmo_uxVw/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1720287771219?e=2147483647&v=beta&t=VkNixDDA6pwlJtM2Ba8xOPoWWEGwFO3FBsOlzu-R1v0",
      "title": "AI-Driven Sales Automation -- The time is now!",
      "author": "",
      "published_date": "Jul 8, 2024"
    },
    {
      "link": "https://www.linkedin.com/pulse/dramatic-roi-ai-sales-process-automation-dmitry-shapiro-ds9tc",
      "image": "https://media.licdn.com/dms/image/v2/D5612AQGvabiginA5QA/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1720285865490?e=2147483647&v=beta&t=LJLoaDtSNkv8E1pmgPo-SlfrHapYbOf5hgil5psbx7Y",
      "title": "Dramatic ROI -- AI Sales Process Automation",
      "author": "",
      "published_date": "Jul 6, 2024"
    },
    {
      "link": "https://www.linkedin.com/pulse/youve-never-seen-before-evolving-software-dmitry-shapiro",
      "image": "https://static.licdn.com/scds/common/u/img/pic/pic_pulse_stock_article_17.jpg",
      "title": "You've never seen this before - evolving software",
      "author": "",
      "published_date": "Sep 16, 2020"
    }
  ],
  "description": {},
  "activities": [
    {
      "link": "https://www.linkedin.com/posts/marquis-sampson_salestips-businessintelligence-companyresearch-activity-7350954619461627905-OkHc",
      "image": "https://media.licdn.com/dms/image/v2/D5605AQHnUxZNQf4nBQ/videocover-high/B56ZgPWGL_HMCI-/0/1752604135536?e=2147483647&v=beta&t=a3RCVDehSZ-YiDn3xClq9lnkblvUeLBeHvxcpc_tnYw",
      "title": "Tired of spending hours researching companies before a meeting? 🕵️‍♂️ Introducing the Cheat Sheet Generator! Your new secret weapon for instant…",
      "activity": "Liked by Dmitry Shapiro"
    }
  ],
  "volunteering": [],
  "certification": [],
  "people_also_viewed": [
    {
      "link": "https://www.linkedin.com/in/hyams?trk=public_profile_browsemap-profile",
      "name": "Chris Hyams",
      "summary": "",
      "location": "Austin, Texas Metropolitan Area"
    },
    {
      "link": "https://www.linkedin.com/in/jonvferrara?trk=public_profile_browsemap-profile",
      "name": "Jon Ferrara",
      "summary": "",
      "location": "Asheville, NC"
    },
    {
      "link": "https://www.linkedin.com/in/hillferguson?trk=public_profile_browsemap-profile",
      "name": "Hill Ferguson",
      "summary": "",
      "location": "San Francisco, CA"
    },
    {
      "link": "https://www.linkedin.com/in/vikas?trk=public_profile_browsemap-profile",
      "name": "Vikas Sharan",
      "summary": "",
      "location": "San Francisco Bay Area"
    },
    {
      "link": "https://www.linkedin.com/in/richardreed1992?trk=public_profile_browsemap-profile",
      "name": "Richard Reed",
      "summary": "",
      "location": "Las Vegas, NV"
    },
    {
      "link": "https://www.linkedin.com/in/mkorsunsky?trk=public_profile_browsemap-profile",
      "name": "Michael Korsunsky",
      "summary": "",
      "location": "Charlotte Metro"
    },
    {
      "link": "https://www.linkedin.com/in/rahulchaturvedimd?trk=public_profile_browsemap-profile",
      "name": "Rahul Chaturvedi",
      "summary": "CEO @ Moolex LLC | Start-ups, R&D, Project Capital, Business Strategy",
      "location": "New York, NY"
    },
    {
      "link": "https://www.linkedin.com/in/foxbrian?trk=public_profile_browsemap-profile",
      "name": "Brian Fox",
      "summary": "",
      "location": "Denver, CO"
    },
    {
      "link": "https://www.linkedin.com/in/drodio?trk=public_profile_browsemap-profile",
      "name": "DROdio - Daniel R. Odio",
      "summary": "",
      "location": "San Francisco Bay Area"
    },
    {
      "link": "https://www.linkedin.com/in/brett-mallory?trk=public_profile_browsemap-profile",
      "name": "Brett Mallory",
      "summary": "",
      "location": "Boston, MA"
    },
    {
      "link": "https://www.linkedin.com/in/jager?trk=public_profile_browsemap-profile",
      "name": "Jager McConnell",
      "summary": "",
      "location": "San Francisco, CA"
    },
    {
      "link": "https://th.linkedin.com/in/jchenard?trk=public_profile_browsemap-profile",
      "name": "Jesse Chenard",
      "summary": "",
      "location": "Amphoe Ban Pong"
    },
    {
      "link": "https://www.linkedin.com/in/davepowell?trk=public_profile_browsemap-profile",
      "name": "Dave Powell",
      "summary": "",
      "location": "Austin, TX"
    },
    {
      "link": "https://www.linkedin.com/in/chris-rothstein-4047012?trk=public_profile_browsemap-profile",
      "name": "Chris Rothstein",
      "summary": "",
      "location": "San Diego, CA"
    },
    {
      "link": "https://il.linkedin.com/in/liadagmon?trk=public_profile_browsemap-profile",
      "name": "Liad Agmon",
      "summary": "",
      "location": "Tel Aviv District, Israel"
    },
    {
      "link": "https://www.linkedin.com/in/masolova?trk=public_profile_browsemap-profile",
      "name": "Elena M.",
      "summary": "",
      "location": "San Francisco Bay Area"
    },
    {
      "link": "https://www.linkedin.com/in/haroldlee?trk=public_profile_browsemap-profile",
      "name": "Harry Lee",
      "summary": "",
      "location": "San Francisco Bay Area"
    },
    {
      "link": "https://www.linkedin.com/in/gt123?trk=public_profile_browsemap-profile",
      "name": "Greg T.",
      "summary": "",
      "location": "Ann Arbor, MI"
    },
    {
      "link": "https://www.linkedin.com/in/mcobrien?trk=public_profile_browsemap-profile",
      "name": "Mike O'Brien",
      "summary": "",
      "location": "Franklin, TN"
    },
    {
      "link": "https://www.linkedin.com/in/sgupta85?trk=public_profile_browsemap-profile",
      "name": "Sunny Gupta",
      "summary": "",
      "location": "Kirkland, WA"
    }
  ],
  "similar_profiles": [
    {
      "link": "https://www.linkedin.com/in/drshapiro?trk=public_profile_samename-profile",
      "name": "Dmitry Shapiro",
      "summary": "",
      "location": "Greater Boston"
    },
    {
      "link": "https://www.linkedin.com/in/dmitryshapiro?trk=public_profile_samename-profile",
      "name": "Dmitry Shapiro",
      "summary": "Problem Solver at cbconstruction",
      "location": "San Francisco, CA"
    },
    {
      "link": "https://www.linkedin.com/in/dmitry-shapiro-8692771?trk=public_profile_samename-profile",
      "name": "Dmitry Shapiro",
      "summary": "",
      "location": "Highland Park, IL"
    },
    {
      "link": "https://www.linkedin.com/in/dmitry-shapiro-10214218?trk=public_profile_samename-profile",
      "name": "Dmitry Shapiro",
      "summary": "--",
      "location": "New York City Metropolitan Area"
    }
  ],
  "recommendations": [
    {
      "link": "https://www.linkedin.com/in/jcuzens?trk=public_profile_recommendations",
      "name": "Jarrod Cuzens",
      "summary": "“Not only is Dmitry one of the most creative and personable individuals I have had the pleasure to work with but he is also one of those people that I will always admire for his ability to come up with and sell these ideas. If I had to sum up Dmitry in one word it would certainly be visionary.”"
    },
    {
      "link": "https://www.linkedin.com/in/sunnygault?trk=public_profile_recommendations",
      "name": "Sunny Gault",
      "summary": "“Dmitry is one of the most unusual CEO's I've ever met- but that's what makes him so great. You feel completely comfortable talking to him and sharing your ideas- which creates an ideal working environment. When you've got a good idea, he commends you for it and gives you the tools you need to go out there and tackle the world!”"
    }
  ],
  "publications": [],
  "courses": [],
  "languages": [
    {
      "name": "Russian",
      "level": "Limited working proficiency"
    },
    {
      "name": "English",
      "level": "Native or bilingual proficiency"
    }
  ],
  "organizations": [],
  "projects": [],
  "awards": [],
  "score": []
}
```

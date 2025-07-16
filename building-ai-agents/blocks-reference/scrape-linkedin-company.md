---
description: Get LinkedIn Company Data
---

# Scrape LinkedIn Company

The Scrape LinkedIn Company block retrieves publicly available information from a LinkedIn company page. This is useful for enriching your workflow with real-time company data — such as industry, employee count, location, and description — without manual lookup.

***

## Configurations

### Company URL

Provide the full URL of the LinkedIn company page you want to scrape.

**Example:** `https://www.linkedin.com/company/mindstudioai/`

{% hint style="danger" %}
Only valid public company pages will return data. Personal profiles or broken URLs will result in errors.
{% endhint %}

***

### Output Variable

Enter the name of the variable to store the scraped data. The returned value will be a structured JSON object.

**Example:** `company_profile`

***

## Sample Output

```json
{
  "company_name": "MindStudio",
  "universal_name_id": "mindstudioai",
  "background_cover_image_url": "https://media.licdn.com/dms/image/v2/D563DAQHsfMJ3A0WRjQ/image-scale_191_1128/image-scale_191_1128/0/1682953888759/youai_ai_cover?e=2147483647&v=beta&t=OQmyNF7EJXFK4-FKvEgxmy7zn-g4P0MsCLubu4TzP_s",
  "linkedin_internal_id": "91188227",
  "profile_photo": "https://media.licdn.com/dms/image/v2/D560BAQHJWyoFxDx2vQ/company-logo_200_200/company-logo_200_200/0/1704388316703/youai_ai_logo?e=2147483647&v=beta&t=2u4H4OT-wjxp9NB44WQVO4AaE429XmlLjBGIKUJLOSs",
  "industry": "Technology, Information and Internet",
  "location": "",
  "tagline": "The fastest way to build AI-powered apps for your team.",
  "company_size_on_linkedin": "Discover all 29",
  "about": "Rapidly build custom AI applications and automations — no coding required.\nEasily mix and match the latest models from OpenAI, Anthropic, Google, Mistral, Meta, and more.",
  "website": "https://mindstudio.ai",
  "industries": "Technology, Information and Internet",
  "company_size": "11-50 employees",
  "headquarters": "",
  "type": "Privately Held",
  "founded": "2023",
  "specialties": "",
  "description": {},
  "locations": [],
  "employees": [
    {
      "employee_photo": "https://media.licdn.com/dms/image/v2/D5603AQHhQ4-UhGgpqA/profile-displayphoto-shrink_100_100/profile-displayphoto-shrink_100_100/0/1708916323677?e=2147483647&v=beta&t=8f09N2sXi6CpaIOvlnEoeGdAidR2gWrOsC1wZLjbC6E",
      "employee_name": "Dmitry Shapiro",
      "employee_position": "",
      "employee_profile_url": "https://www.linkedin.com/in/dmitry-shapiro-a2b1?trk=org-employees"
    },
    {
      "employee_photo": "https://media.licdn.com/dms/image/v2/D4E03AQHFqAOAyv6d1g/profile-displayphoto-shrink_100_100/B4EZbakNBNGkAU-/0/1747423646207?e=2147483647&v=beta&t=uqATJggybaqd-MsnJoDxM2ZPnmZTFSRXmeUUHMAboKo",
      "employee_name": "Aleksandar Pokrajac",
      "employee_position": "AI Innovation PM | Custom AI Solutions",
      "employee_profile_url": "https://rs.linkedin.com/in/pokrajac?trk=org-employees"
    },
    {
      "employee_photo": "https://media.licdn.com/dms/image/v2/D4D03AQEoOkPm9qMz4g/profile-displayphoto-scale_100_100/B4DZfFY.REH4Ag-/0/1751363348177?e=2147483647&v=beta&t=ZE49EIlCvWMKIn3EbImELcktUu8MSCKIGTD940x4Obc",
      "employee_name": "Gary Seath",
      "employee_position": "I help business people to connect with eachother. Who would you like to connect with?",
      "employee_profile_url": "https://za.linkedin.com/in/gary-seath?trk=org-employees"
    },
    {
      "employee_photo": "https://media.licdn.com/dms/image/v2/D4D03AQGUNXSrPOMSRQ/profile-displayphoto-shrink_100_100/B4DZU0NfqGG8AU-/0/1740337709318?e=2147483647&v=beta&t=7PSR7s8uGKlJ5z3Kgx251rPbIEcJBL9mxF1W-pIJgyk",
      "employee_name": "Jonathan M K.",
      "employee_position": "Head of GTM Growth Momentum | Founder GTM AI Academy & Cofounder AI Business Network | Business impact > Learning Tools | Proud Dad of Twins",
      "employee_profile_url": "https://www.linkedin.com/in/jmkmba?trk=org-employees"
    }
  ],
  "updates": [
    {
      "text": "New Fetch Slack Channel History block makes it easy to pull messages from a Slack channel into a MindStudio AI Agent and generate reports, analyze them, create summaries, etc.\n\nAvailable today, check it out!",
      "article_posted_date": "5d",
      "total_likes": "25",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "MindStudio University is live! 🎓\n\nIn MindStudio University, you'll find over 6 hours of step-by-step, in-depth tutorials on building AI agents. Hundreds of people have already levelled up their AI skills with our video courses. \n\nBookmark the link below!",
      "article_posted_date": "2w",
      "total_likes": "48",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "You could spend thousands of dollars testing ad copy... or you could use this agent to find the winning formula. \n\nExpert marketer Justin Brooke walks through it below.\nHow I built an AI agent that predicts winning ad copy BEFORE spending a dime...\n\nIf you could predict lottery numbers... would you?\n\nWell then, if you could predict winning ads... would you?\n\nLet me explain how it works...\n\nFirst, we trained an agent on all our customer data. We give our ad copy (or blog post, whatever you want) to the first agent. Which gives us feedback on the ad creative based on all our customer data.\n\nIt's so real, that it feels like I'm reading an actual customer support ticket from a real customer.\n\nThe feedback alone is amazing to learn from if you're not a great writer yet.\n\nBut then we take the original ad creative + feedback, and we send that to another agent that is trained on world class direct response copywriting tactics.\n\nIt then writes use 3 new variations for our original ad creative, based on our customers feedback. This is just like they used to do with focus groups and customer development calls - but with ai and automated.\n\nIf all it did was pump out expertly written variations (based on actual customer data) this would be worth gold, but we go another step.\n\nWe want to know which variation is statistically likely to outperform the others, so we push the feedback + variations to a data analyst agent to assign scores.\n\nScoring is based on how well the ad fits our customer data, the feedback from our customer simulator agent, and all known best practices for advertising.\n\nFinally, the data analyst agent pushes the Success Probability Score for each variation and the winning variation to the screen for the user to deploy.\n\nVOILA... Now your cousin Marv can write ads for you and with this machine it'll improve it based on actual market data, get 3 revisions by an expert, and then predict which revision is most likely to win.\n\nIf that's not worth millions, I don't know what is!\n\nIf you want to see the prompts and structure of how I built this, just comment \"agent\" below, and I'll DM you a loom video of how it works. MUST BE CONNECTED for me to be able to DM you.",
      "article_posted_date": "2w",
      "total_likes": "5",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "Build the tools that make your team call you an \"AI savant\" like David Cohn. \n\nKudos to Advance Local for being at the forefront of AI in journalism. They use nearly 300 MindStudio agents, like this one, in their newsrooms. An AI Tool I built is getting some praise/love from the Editor/VP of content at cleveland.com / The Plain Dealer. It's called \"Editor's Eyes\" and they are now running all their stories through it before publishing. \n\nhttps://lnkd.in/gx7wa-ng\n\n\"Starting this month, anyone in our newsroom who writes – including me -- must run their work through a tool we’ve developed to clean it up. It’s a tool called Editor’s Eyes, developed in-house by David Cohn, the AI savant for our parent company, Advance Local. David has taken our breath away with the number of tools he has developed for us this year.\nWriters need only paste their work into the tool, and seconds later they get a list of fixes they can make, with advice for making it read better. In effect, it gives every writer their own personal copy desk.\"\n\nA big shoutout to Christopher Quinn who embraces the changing landscape like a real leader. And to all the colleagues at Cleveland (and Advance throughout). You all keep me motivated and pumped for more.",
      "article_posted_date": "2w",
      "total_likes": "4",
      "article_title": "Cleveland OH Local News, Breaking News, Sports & Weather",
      "article_sub_title": "cleveland.com",
      "article_link": "https://www.linkedin.com/redir/redirect?url=https%3A%2F%2Fwww%2Ecleveland%2Ecom&urlhash=XJDJ&trk=organization_guest_main-feed-card_reshare_feed-article-content",
      "article_image": "https://media.licdn.com/dms/image/sync/v2/D5627AQFOr8xR0NqxvA/articleshare-shrink_1280_800/B56ZdeRUriGoAQ-/0/1749633289341?e=2147483647&v=beta&t=-iv_bcxztTop5Xe0-FHWc9YgRxYyHDw4M7D940QsXng"
    },
    {
      "text": "📸 𝗜𝗺𝗮𝗴𝗲𝗻 𝟰 𝗶𝘀 𝗻𝗼𝘄 𝗮𝘃𝗮𝗶𝗹𝗮𝗯𝗹𝗲 𝗼𝗻 𝗠𝗶𝗻𝗱𝗦𝘁𝘂𝗱𝗶𝗼!\nWe're thrilled to announce the launch of 𝗚𝗼𝗼𝗴𝗹𝗲'𝘀 𝗜𝗺𝗮𝗴𝗲𝗻 𝟰—the latest and most advanced text-to-image model—𝗻𝗼𝘄 𝗹𝗶𝘃𝗲 𝗼𝗻 𝗠𝗶𝗻𝗱𝗦𝘁𝘂𝗱𝗶𝗼.\n\nWhether you're an artist, a product designer, a marketer, or just curious, you can now generate 𝗽𝗵𝗼𝘁𝗼𝗿𝗲𝗮𝗹𝗶𝘀𝘁𝗶𝗰, 𝗵𝗶𝗴𝗵-𝗿𝗲𝘀𝗼𝗹𝘂𝘁𝗶𝗼𝗻 𝘃𝗶𝘀𝘂𝗮𝗹𝘀 from text with unprecedented fidelity—directly inside your AI workflows. \n\n✨ 𝗪𝗵𝘆 𝗜𝗺𝗮𝗴𝗲𝗻 𝟰?\n\n🖼️ - 𝗣𝗵𝗼𝘁𝗼-𝗿𝗲𝗮𝗹𝗶𝘀𝗺 that rivals actual photography\n🔍 - 𝗦𝗵𝗮𝗿𝗽𝗲𝗿 𝗰𝗹𝗮𝗿𝗶𝘁𝘆 and 𝗶𝗺𝗽𝗿𝗼𝘃𝗲𝗱 𝘁𝗲𝘅𝘁 𝗿𝗲𝗻𝗱𝗲𝗿𝗶𝗻𝗴\n🔠 - 𝗔𝗱𝘃𝗮𝗻𝗰𝗲𝗱 𝘀𝗽𝗲𝗹𝗹𝗶𝗻𝗴 𝗮𝗻𝗱 𝘁𝘆𝗽𝗼𝗴𝗿𝗮𝗽𝗵𝘆 for comics, packaging, and design\n🎨 - 𝗦𝘂𝗽𝗽𝗼𝗿𝘁𝘀 𝗱𝗶𝘃𝗲𝗿𝘀𝗲 𝘀𝘁𝘆𝗹𝗲𝘀: from macro wildlife photography to vintage illustrations, impressionism, 3D renders, and more\n\n🌟  𝗧𝗿𝘆 𝗶𝘁 𝗻𝗼𝘄: mindstudio.ai → Create → Generate Image\n\n Let your imagination do the talking. We'll take care of the rendering.",
      "article_posted_date": "2w",
      "total_likes": "29",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "Students, recent grads & dropouts: the #1 skill you can learn right now → building AI agents. \n\nYour school isn't teaching the skills companies are desperate for... but we are. \n\nJoin the next cohort with our CEO, Dmitry Shapiro, to build your AI portfolio and connect with employers who are looking for talent.College students, recent college graduates, parents of college students...\n\nI am teaching a free 2 week course -- Learn to build AI agents — the most in-demand skill today!\n\nHere’s how it works:\n\nDuration: 2 weeks\nFormat: Virtual (Zoom-based training + self-paced projects)\nTime commitment: ~10 hours (a few 1-hour Zoom sessions + project work)\nTools: You’ll use MindStudio to build real AI agents\nCost: Completely free\nSpots: Limited (20–40 per cohort)\n\nMore details in comments 👇\n\nWho else should know about this? @ mention them.",
      "article_posted_date": "3w",
      "total_likes": "4",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "After leading tech teams at Walmart, Yahoo, and Strava, Claude Jones and the others behind the San Diego Tech Hub are launching do.it.withAI, a community-based platform to train AI builders. \n\nTheir first AI bootcamp is free, and powered by MindStudio. \n\nApply below!👋 Hey Community! \n\nI’m back… and ready to make an impact.\n\nAfter being let go from Centr, I finally had space to reflect. Not just on what I wanted to do next, but on what people around me were struggling with.\n\nIn every conversation with friends, colleagues, and community members, one theme kept surfacing: AI is already transforming how we live and work, and for many, it's creating real fear.\n\nNot just fear of being replaced, but fear of being left behind.  For many, it’s not even about job loss. It’s about not knowing where to start or how to keep up.\nThat stuck with me.  Because I’ve felt it too.\n\nWhat people need isn’t just access to AI tools.  They need agency — the power to learn, build, and adapt on their own terms.\n\nSo I got together with some San Diego Tech Hub conduits, and we created do.it.withAI, a community-driven platform built to train the next generation of AI Agent Builders.\n\nWe’ve partnered with Dmitry Shapiro at MindStudio to launch a free live pilot AI Bootcamp, limited to 100 participants.\n\nThis isn’t a giveaway. It’s a co-build. Your experience and feedback will help shape how we train the next generation of AI Agent Builders.\n\n🎥 Check out the video below to see what we’ve been building. 👇 \n\nOh, before I go, two quick points: \n\n1. If this resonated, share it. Someone in your network might need it.\n2. If you’re ready to build or brainstorm, DM me. Let’s make moves.\n\n#AI #Community #TechForGood #DoItWithAI #AgencyOverAccess #AIAgents\n\nNotes: site built with Lovable, Supabase, ChatGPT, and Human creativity in the loop.",
      "article_posted_date": "3w",
      "total_likes": "5",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "The UK Government is going deep on AI—and MindStudio is right at the center. \n\nYesterday, we led a hands-on session with the Incubator for Artificial Intelligence, an agile team inside the government, tasked with scaling AI tools across departments. Their mission: use AI to drive public good.\n\nIn an hour, they built working AI agents with MindStudio. Real prototypes for real public sector problems.\n\nThis is the playbook for modern governments:\n\n🛠️ Lightweight tools – skip the external contracts\n🔑 Broad access – let teams solve their own problems\n⚡ Fast results – prototypes in hours, not months\n\nMindStudio makes it happen.",
      "article_posted_date": "1mo",
      "total_likes": "22",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "Now available: Use Self-Hosted Models in your AI agents 🧠\n\nYou can now connect your own self-hosted AI models — whether they’re running locally on your device or hosted in the cloud. Works for any OpenAI-compatible model.\n\nMindStudio already gives you access to 150+ models out of the box — Claude 4, GPT-4o, and more — no API keys required.\n\nNow you can go beyond the flagships and bring your own.\n\n🛠️ Just tinkering? It’s included in MindStudio Pro for personal use.\n🏢 Deploying for business? Get in touch with us about Enterprise.",
      "article_posted_date": "1mo",
      "total_likes": "23",
      "article_title": "",
      "article_sub_title": ""
    },
    {
      "text": "Just shipped: 11 new blocks for transforming text in MindStudio 🔁\n\nEverything you actually need to do with text — now built in.\nNo prompt required. Just drop the block in and go.\n\nHere’s what’s new:\n\n📝 Summarize Text – Get the TL;DR\n\n🧠 Improve Writing – Fix spelling, grammar, clarity\n\n🌍 Translate Text – Any language, instantly\n\n👥 Rewrite for Audience – Adapt for different personas\n\n🎓 Convert Reading Level – Make it simpler or more advanced\n\n🔀 Merge Text – Combine multiple inputs into one\n\n💬 Adjust Tone – Casual, formal, fun — your call\n\n✅ Align to Brand – Stay on voice, every time\n\n✏️ Rewrite Text – Give it a rule, and it’ll rewrite at scale\n\n🧱 Convert to Format – Repurpose content into a blog, email, post — whatever you need\n\n🧹 Extract from Text – Cleanly pull structured info from messy input\n\nLive now on MindStudio.",
      "article_posted_date": "1mo\n  \n                      \n                      \n                        Edited",
      "total_likes": "14",
      "article_title": "",
      "article_sub_title": ""
    }
  ],
  "similar_companies": [
    {
      "link": "https://nl.linkedin.com/company/jaide-ai?trk=similar-pages",
      "name": "Jaide AI",
      "summary": "Software Development",
      "location": "Reeuwijk, Zuid holland"
    },
    {
      "link": "https://www.linkedin.com/company/syntheticusers?trk=similar-pages",
      "name": "Synthetic Users",
      "summary": "Technology, Information and Internet",
      "location": "Technology, Information and Internet"
    },
    {
      "link": "https://www.linkedin.com/company/withkoji?trk=similar-pages",
      "name": "Koji",
      "summary": "Technology, Information and Internet",
      "location": "San Diego, CA"
    },
    {
      "link": "https://cz.linkedin.com/company/itsmakehq?trk=similar-pages",
      "name": "Make",
      "summary": "Software Development",
      "location": "Prague, Praha 8"
    },
    {
      "link": "https://www.linkedin.com/company/perplexity-ai?trk=similar-pages",
      "name": "Perplexity",
      "summary": "Software Development",
      "location": "San Francisco, California"
    },
    {
      "link": "https://www.linkedin.com/company/gamma-app?trk=similar-pages",
      "name": "Gamma",
      "summary": "Software Development",
      "location": "Software Development"
    },
    {
      "link": "https://dk.linkedin.com/company/uizard?trk=similar-pages",
      "name": "Uizard by Miro Labs",
      "summary": "Software Development",
      "location": "Software Development"
    },
    {
      "link": "https://www.linkedin.com/company/flowiseai?trk=similar-pages",
      "name": "FlowiseAI (YC S23)",
      "summary": "Software Development",
      "location": "San Francisco, California"
    },
    {
      "link": "https://www.linkedin.com/company/hunchtools?trk=similar-pages",
      "name": "Hunch",
      "summary": "Technology, Information and Internet",
      "location": "San Francisco, California"
    },
    {
      "link": "https://www.linkedin.com/company/workera-ai?trk=similar-pages",
      "name": "Workera",
      "summary": "Technology, Information and Internet",
      "location": "Palo Alto, California"
    }
  ],
  "affiliated_companies": [],
  "product": []
}
```

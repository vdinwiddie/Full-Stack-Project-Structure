# Logistics  

**Q1:** At what time in the week would your group be available to meet online?\
**Answer:**
Our group would be avaiable to meet online on Fridays in the afternoon/evening. As well, we will have another weekly meeting during the weekend since we are most flexible then.

---

# Timeline: Weekly Meeting Goals  

**Q2:** What is your goals that your group want to achieve in each weekly meeting?\
**Answer:**\
Prior to 10/30: We plan to finalize our ideas and pick
Prior to 11/6: We plan to gather the api and publicly available databases we need to do what we need.
Prior to 11/11: We plan to have a rudimentary bare bones app up and running. Complete functionality is not necessary.
Prior to 11/13: We plan to have a checkup/revision session about how to implement our app features, and do them. 
Prior to 11/20: We plan to have an app ready to go for the most part, just revising and polishing up any areas that need improvement.

---

# Communication  

**Q3a:** How can your group communicate when doing the Full Stack Group Project?  
**Q3b:** What are the usernames of each group member on that platform?  
**Q3c:** What is your group's expected response time to messages?  

**Answer:**\
Q3a: We will communicate via Discord. We will faciliate this through Direct messaging and voice calls.\
Q3b: Our usernames are RJ_25 for Jewel, 30cw1-0xn for Isaac, and Gerbil Party for Vinnie.\
Q3c: During business hours, within an hour. During off time, within 24 hours.

---

# Norms  

**Q4a:** How will your group handle situations when there is conflict in your group?  
**Q4b:** How will your group handle situations when a member is not contributing enough?  

**Answer:**\
**Q4a:** If there is disagreement on direction, we will simply hold a binary vote. There are 3 of us, so there cannot be a tiebreaker. Once the decision is made, we act accordingly. We understand nothing is personal, it just academic bureaucracy. Business, nothing personal. \
**Q4b:** If a group member is not contributing enough, we will make this clear to each other. We are all grown adults. We don't have to beat around the bush or give a run around. If there is an issue, we inform each other, constructively provided a timeline of what we would like done, shake hands, and walk away. Again, it's purely academic, nothing personal. And of course, this doesn't include the collaboration and assistance we provide to one another.

---

# Roles  

**Q5:** How will your group divide your role in the Group Project?\
**Answer:**
Vinnie has been designated as the Frontend specilist, Jewel has been appointed as the backend specialist, and I am just the projet support. Although this is a general idea of our individual directions, we plan total hands-on colloboration on all aspects of this project from everyone.

---

# Tech Stacks

**Q6:**Which tech stacks will your group use? (Django + React or Flask + React)
**Answer:** We will be using Django + React. 

---
# Full Stack Group Project Track  

---

# Track 1: Tackling Generative AI Consequences

*Keywords: copyright, security, misinformation, bias, ethics*

**Problem 1:** \
Generative AI APIs are vulnerable to direct and indirect prompt injection attacks, allowing bad actors to extract secrets, bypass safety filters, or execute malicious system instructions.
**Solution 1:** Jailbreak & Prompt Injection Defense Gateway\
Build a lightweight middle-layer firewall API that inspects incoming user prompts against known adversarial vectors, structural patterns, and semantic anomalies before passing them to an LLM. (Also thinking about how gemini, for our CS 351 labs, would give up and give you the answers eventually if bugged it enough in the right way, despite the initial restrictive prompt provided.)
**Problem 2:** 
Independent authors and bloggers risk having their paywalled or original prose scraped by Web crawlers for LLM training without attribution.
**Solution 2:** Adversarial Data Cloaking for Text. Ascii to unicode-look-alike to confuse AI tokenizers\
A browser extension/tool that injects imperceptible homoglyphs (visually identical Unicode characters) or subtle syntactic perturbations into web text. To readers, it looks normal; to web scrapers feeding tokenizers, it breaks token semantics or introduces invisible tracking signatures.

---

# Track 2: Technology for Public Goods 

*Keywords: community, accessibility, sustainability, environment, public health, education, civic data, social impact*

**Problem 3:**
High volumes of perishable food from local markets and dining halls are discarded daily, while nearby community fridges sit empty. Coordination happens via informal group chats, leading to wasted driver trips or uncollected surplus food reaching its expiration date.
**Solution 3:**  
Food Rescue & Community Fridge Dispatch Network\
A dispatch hub connecting food donors with neighborhood drivers and community fridges. Donors post surplus inventory with expiration countdowns; volunteers claim pickup routes optimized for urgency and location.
**Problem 4:** 
Bike theft is rampant around UIC, and official racks are often full or targeted by thieves. When forced to use informal anchors like fences or trees, standard U-locks often don't physically fit, leaving students to default to easily snip-able cable locks with no warning about active theft hotspots.
**Solution 4:** SecureCycle UIC (Crowdsourced Micro-Parking & Security Map) \ 
This is accessiblity oriented, and will feature, bike-rack locations(official and unofficial), bike theft hotspots, lock usability, etc. A crowdsourced campus web app that maps official racks alongside viable alternative anchors (fences, posts, trees) filtered by physical lock compatibility (U-lock, chain, folding). Students report cut locks and thefts in real time to generate active risk alerts before parking.

---

# Idea Finalization

**Q7: From the 4 project ideas you have above, please choose one project that you are going with for the rest of the semester. Explain why you are going with that project.**
**Answer:** We are going to do the bike parking and security project becaues this is personally interesting since we go to UIC and would like to serve our campus as well in anyway, small or big.

**Q8: Which two advanced data structures or algorithms from the Milestone 3 list do you plan to use — one from Group 1 and one from Group 2? For each, name the specific question your application needs to answer, and say why that structure is the right shape for it. (Plain DFS, BFS, and Dijkstra do not count. This is a plan, not a commitment — you may change it later as long as you explain why in Milestone 3.)**
**Answer:** For group 1: Priority Queue (Max-Heap) Spot Security Scoring (Priority Queue). Every parking anchor (official rack, fence, tree) gets a dynamic Risk Score calculated from recent theft reports, camera visibility, and lighting quality. The root always hold the highest risk score parking spot. This matters becaues when a student searches for parking, the app instantly pops the highest-risk spots from the heap to display prominent warnings ("⚠️ High Theft Hazard Nearby") before placing them on the map. As students log new cut-lock reports, the heap dynamically updates spot scores via increase_key operations.

For group 2: Disjoint Set Union (Union-Find) to automatically group individual theft and cut-lock reports into dynamic "theft hotspot clusters" as new pins are submitted. An A Search / Spatial Graph* can route students along the best-lit campus paths to the nearest secure anchor. This is good because we can then have different groups for different locations, becaues the ARC will have it's own group of bike-locations, but so will BSB, and so will University Hall, so we can show local hotspots, but also aggregate them.

---

# Extra Credit (Only do this if you are done with Idea Finalization)

## Database Design

**Q1: What database are you using for your project (SQLite, PostgreSQL, noSQL, MongoDB,...), and why do you choose it?**
We will be using MongoDB because it is common, and flexble enough to easily accommdate our user generated data since this is a crowd-sources app. 
**Q2: How will database be helpful to your project? How will you design your database to support your application features?**
MongoDB allows us to perform efficient 2D Spatial Queries (using 2dsphere geospatial indexing) to find nearby parking anchors within a given radius of a student's location.
## Third-Party API Integration

**Q3: Which third-party API(s) will you integrate into your project? What data will you pull from the API(s), and how will you use it in your application?**
OpenStreetMap / Mapbox API: We will pull interactive map tiles, geocoding/building search data (e.g., "ARC", "BSB", "SEO"), and pedestrian walkway path geometries to render map layers and calculate walking routes.\

City of Chicago Data Portal (Socrata API - Crimes Dataset): We will pull historical municipal bike theft incidents (filtered by IUCR crime code 0610 / THEFT around the UIC campus district). This seeds our initial risk scores across campus before user crowdsourcing fills in recent gaps.
**Q4: Does your API key has limitations such as rate limits or downtime? How are you going to deal with that?**
Yes, APIs like Mapbox and the Chicago Data Portal enforce rate limits (e.g., requests per minute). On the front end, search input queries (e.g., building autocomplete) will be debounced (waiting 300ms after typing stops) to prevent API spam. This is related to debouncing & dethrottling, apparently.
## Authentication and Security

**Q5: What authentication method will you use (e.g., username/password, OAuth, JWT)?**
We will use username/password.
**Q6: How will you store and protect sensitive user data (e.g., passwords, tokens)?**
\We will protect it with tokens or hashing. Passwords and other sensitive data will never be stored as plaintext. 
## Deployment

**Q7: Where will you deploy your project (e.g., Heroku, AWS, Render)? How will you manage environment variables and secrets during deployment?**
We will deploy our web application using Render (or Vercel for the front end and Render for the backend Node/Express API), with MongoDB Atlas hosting the database.
Secrets (such as DATABASE_URI, JWT_SECRET, and MAPBOX_API_KEY) will be managed strictly using environment variables (process.env). They will be injected through the deployment platform's environment settings dashboard during build time and maintained locally in a .env file that is ignored by Git (.gitignore).
**Q8: How will you ensure your deployment is reliable and easy to update?**
We will connect our GitHub repository directly to Render/Vercel. Pushing changes to the main branch triggers automated build tests and deployment pipeline execution.

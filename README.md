# saka-ai-outreach-lead-system
AI-powered cold outreach automation system


🔍 System Flow
![Cold Email Lead System Flow](./docs/cold_email_lead_flow.png)


1. Scrape leads using Apollo search → Apify actor  
2. Add scraped leads to Google Sheets  
3. Filter & loop through rows in Make.com  
4. Run GPT-4 to generate:
   - Personal research
   - Company insight
   - Cold email copy  
5. Send via Gmail module  
6. Update the row with sent timestamp & status  
7. [Optional] Follow-up logic or reply detection


⚙️ How to Use

1. 🔑 Connect accounts: Gmail, Apify, OpenAI, Google Sheets  
2. 📄 Copy the sheet-template provided  
3. 🧠 Import the GPT prompts from `/prompts/`  
4. 📤 Import the Make.com blueprint  
5. 🎯 Customize filters, targeting, and niche prompts  
6. 🟢 Run manually or schedule



#🧠 GPT Prompts Included

Located in `/prompts/`:

 `prospect_research.md`
 `company_research.md`
 `personalized_email.md`

All prompts use clean variable insertion like `{{first_name}}`, `{{job_title}}`, `{{company_website}}`, etc.



🧩 Optional Add-ons (Customizable)

🔁 Inbox rotation  
📨 Follow-up email flows  
📥 Gmail reply detection  
📊 Google Data Studio dashboard  
🔗 CRM integration (HubSpot, Pipedrive)  
🧑‍💼 LinkedIn scraping via PhantomBuster  



📸 Screenshots

See `/docs/` for system visuals, spreadsheet structure, and flow diagram.


📬 Want a Live Demo?

DM me on LinkedIn or email at learnwithideas@gmail.com
You’ll receive:
 ✅ Loom walkthrough
 ✅ Setup checklist
 ✅ Custom quote if needed

 🔐 License

MIT (or Private Use Only — depending on your needs)



 🤝 Credits

Built with ❤️ by [Anees @ SAKA.AI]


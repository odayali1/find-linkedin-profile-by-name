# Find a LinkedIn profile from a name and company

Find a LinkedIn profile when you know the person's name and employer. This example reads that CSV, runs **LinkedIn Profile Finder by Name & Company** with the name, company, and job title strategy, and saves the profile URL.

The code in this repository calls a published [Mawsool](https://mawsool.tech) Actor on [Apify](https://apify.com/oday). You use your own Apify token. The run is billed on Apify. Mawsool does not receive your CRM export, only the lookup you submit to the Actor.

**Start on Apify:** [LinkedIn Profile Finder by Name & Company](https://apify.com/oday/mawsool-linkedin-profile-finder)

**Talk to Mawsool:** info@mawsool.tech · osama@mawsool.tech · https://mawsool.tech

## How do I run it?

```bash
pip install -r requirements.txt
python enrich.py examples/input.csv --dry-run
set APIFY_TOKEN=your_apify_token
python enrich.py examples/input.csv --out results.json
```

On macOS or Linux, use `export APIFY_TOKEN=your_apify_token`.

Create the token at [Apify integrations](https://console.apify.com/settings/integrations). The example sends `matchStrategy` `name_company_job_title`, which is the right choice when the CSV has no profile URL.

## What does the CSV look like?

Required columns are `firstName`, `lastName`, and `company`. `jobTitle` is optional and improves the match.

```csv
firstName,lastName,company,jobTitle
Ada,Example,Example Inc,VP Sales
```

## What do I get back?

Each result row includes the name and company you sent, `hasLinkedIn`, `linkedinUrl`, `headline`, `matchedCompany`, and `matchType`. A row without a confirmed profile is returned as no match.

When you already have the profile URL and want the longer profile record, run [LinkedIn Profile Details from URL](https://apify.com/oday/mawsool-linkedin-profile-details). For a large file, use [Mass LinkedIn Profile Scraper](https://apify.com/oday/mawsool-mass-linkedin-profile-scraper).

## How much does it cost?

Name and company lookup starts at about $1 per 1,000 on the [Actor page](https://apify.com/oday/mawsool-linkedin-profile-finder). Profile details for URLs you already have start at $1.80 per 1,000. The current price is always on the Actor page. Paid Apify plans receive the plan discount shown there.

`cost = rows processed × your plan price per row`.

## Which Mawsool Actor should I use?

- [Email to LinkedIn Finder](https://apify.com/oday/mawsool-email-linkedin-lookup)
- [LinkedIn Profile Finder by Name & Company](https://apify.com/oday/mawsool-linkedin-profile-finder)
- [LinkedIn Profile Details from URL](https://apify.com/oday/mawsool-linkedin-profile-details)
- [Mass LinkedIn Profile Scraper](https://apify.com/oday/mawsool-mass-linkedin-profile-scraper)
- [LinkedIn Current Company Checker](https://apify.com/oday/mawsool-linkedin-company-checker)
- [LinkedIn Job Change Detector](https://apify.com/oday/mawsool-linkedin-job-change-watch)
- [LinkedIn Company Details from URL](https://apify.com/oday/mawsool-linkedin-company-details)
- [Mass LinkedIn Company Scraper](https://apify.com/oday/mawsool-mass-linkedin-company-scraper)

## Related example clients

- [linkedin-email-to-profile](https://github.com/odayali1/linkedin-email-to-profile)
- [linkedin-job-change-checker](https://github.com/odayali1/linkedin-job-change-checker)
- [linkedin-company-enrichment](https://github.com/odayali1/linkedin-company-enrichment)

## Does this repository include Mawsool's data service?

No. This is an open-source example of how to start the public Actor and save the dataset. The Actor page is the product. For a data partnership, email info@mawsool.tech or osama@mawsool.tech.

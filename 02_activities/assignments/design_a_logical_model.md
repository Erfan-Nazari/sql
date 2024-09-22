# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).
![Question_1](https://github.com/Erfan-Nazari/sql/blob/model-design/02_activities/assignments/Question_1.png)

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.
![Question_2](https://github.com/Erfan-Nazari/sql/blob/model-design/02_activities/assignments/Question_2.png)

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Type 1 slowly changing dimensions is the method that overwrites the existing value with the new value and does not retain history. A new table [customer_address] will be created with the following columns:

customer_id (Primary Key and also Foreign Key from the customer table)
street_number
street_name
apt_or_unit (Nullable)
city
province
postal_code
country

 Type 2 slowly changing dimensions is the method that adds a new row for the new value and maintains the existing row for historical and reporting purposes. A new table [customer_address] will be created with the following columns:

address_id (Primary Key)
customer_id (Foreign Key from the customer table)
street_number
street_name
apt_or_unit (Nullable)
city
province
postal_code
country
start_date
end_date (Nullable: NULL if the address is current)
```

## Question 4
Review the AdventureWorks Schema [here](https://imgur.com/a/u0m8fX6)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
The AdventureWorks schema is much larger than my ERD. It has more tables and its tables have more columns than mine. In general, it is more complex and it has more detailed information. My ERD is simpler and focus on essential tables and columns.

Anther difference is that my ERD is designed for a small in-person bookstore while the AdventureWorks schema is designed for a larger bookstore which has online features like password for logging in or shipping information (like shippping rate) for purchases.

Another important difference is that the AdventureWorks schema is divided into logical blocks Sales, Purchasing, Person, Production, HumanResources, and dbo, each containing a group of related tables. My ERD does't have this division into blocks because it is much smaller and it only contains a few tables.

If we need a very simple design focusing on essential tables and columns, my ERD is good enough. But depending on our needs, we may add some of the features from the AdventureWorks schema to our design.
```

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `September 28, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-4-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.

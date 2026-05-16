# Platos Health — User Behaviour & Health Outcomes Analysis

**Author:** Muoneke Donmoen Nwamba | [LinkedIn](https://www.linkedin.com/in/muoneke-nwamba) | [GitHub](https://github.com/Neksperfect)

---

## What This Project Is About

Platos Health is a digital health platform that helps users track their health over time. This was a technical assessment where I was given three datasets and asked to answer one core question:

> Are users actually getting value from the platform, and what does the data tell us about why some do and some don't?

To answer that I looked at three things: how users sign up, whether they come back after signing up, and whether the ones who stay are actually getting healthier.

I also reviewed a set of AI generated health messages the platform sends to users and assessed whether they were safe, accurate and appropriate to send.

---

## The Data

Three datasets were provided:

| Dataset | What It Contains |
|---|---|
| App Events | Every action a user takes in the app, timestamped |
| User Profiles | Signup date, country, age band, gender, subscription tier, referral source |
| Health Outcomes | Weight, BMI, and body fat readings over time |

**Dataset size:** Not publicly disclosed (private company assessment)
**Missing data:** Body fat percentage was only available for users with a connected device

---

## What I Did

### 1. Cleaned the Data First

Before any analysis, I dealt with a few quality issues:

- Removed duplicate event records that would have caused overcounting
- Standardised inconsistent text values such as referral source names with different capitalisation
- Converted all timestamps into a consistent format for time based analysis

### 2. Activation Funnel Analysis

I mapped out the five stages every new user goes through when signing up:

```
Signup Started → Verification Started → Verification Completed → Profile Setup → Signup Completed
```

The biggest drop off happened between verification start and verification completion. Most users who started the process did not finish it at this step.

I also went beyond signup completion to define what "fully activated" actually means. A user was considered truly activated only when they completed signup AND did at least one meaningful thing in the app, such as opening it, recording a health reading, or connecting a device. Just creating an account does not mean someone has started using the product.

### 3. Retention Analysis

I grouped users by the week they signed up and tracked how many came back the week after.

Key finding: roughly half of new users return in their first week. But more importantly, users who engaged more in the first 14 days were significantly more likely to still be active weeks later.

Users were placed into three groups based on early activity:

| Engagement Group | Description |
|---|---|
| High Engagement | Frequent app interactions in the first two weeks |
| Moderate Engagement | Some activity but inconsistent |
| Low Engagement | Little or no activity after signing up |

The pattern was clear. The more a user does early, the more likely they are to stick around.

### 4. Health Outcomes Analysis

I tracked weight and BMI trends over up to 12 weeks for users who recorded measurements.

A meaningful improvement was defined as a 5% reduction in weight from the user's starting measurement. This threshold is a commonly used benchmark in health research and separates real change from normal daily variation.

Users who hit this threshold were compared with those who did not to see if their behaviour in the app looked different.

Note: Body fat analysis was limited to users with connected devices since manual logging does not capture this metric.

### 5. AI Insight Quality Review

This was the most interesting part of the assessment. I reviewed five AI generated health messages that the platform sends to users and rated each one for accuracy, tone, clarity and safety.

| Insight | Rating | Reason |
|---|---|---|
| A | Needs Edit | Encouraging but vague. "Keep up whatever you're doing" could read as medical advice |
| B | Fail | A 0.4% body fat change is likely measurement noise. Flagging it as a possible metabolic issue could worry users unnecessarily |
| C | Needs Edit | Comparing the user to "most users" is discouraging and unhelpful |
| D | Pass | Clear, specific, links the improvement to real behaviours. Well done |
| E | Needs Edit | Slightly negative in tone when no data is recorded. Easy to reframe constructively |

For each message that needed editing I wrote an improved version that kept the intent but removed the risk.

---

## Key Findings

**1. The verification step is where most users give up**
This is the single biggest friction point in onboarding. Fixing it could meaningfully increase the number of users who actually activate.

**2. The first two weeks make or break retention**
Users who engage early stay. Users who do not engage early mostly do not come back. This window is the most important period in the user journey.

**3. Some users are showing real health improvement**
Among users who record measurements consistently, a portion show meaningful weight reduction over 12 weeks. Engaged users are more likely to be in this group.

**4. Not all AI health messages are safe to send as written**
Only one of five messages passed review without changes. The others ranged from vague to potentially harmful. In a health context this matters because users may act on what the platform tells them.

---

## Assumptions Made

- A user counted as retained if they had at least one app event in the week after signup
- Engagement level was based on activity in the first 14 days
- Meaningful health improvement was set at a 5% weight reduction from baseline
- Device and manually logged readings were assumed to be accurate

---

## Limitations

- Patterns in the data do not prove cause and effect
- Users who connect devices may already be more motivated than average, which could skew the health outcomes results
- Body fat analysis only covers users with connected devices
- The dataset covers a limited time period

---

## Tools Used

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)

- **Analysis:** Python, Pandas
- **Visualisation:** Power BI
- **Documentation:** Full process documentation and executive summary produced alongside the analysis

---

## Files in This Repository

```
├── README.md                               # You are here
├── platos.pbix                             # Power BI dashboard file
├── platos_health_analysis.ipynb            # Analysis file
├── platos_health_executive_summary.pptx    # Executive summary presentation
└── platos_health_process_documentation.    # Full process and methodology documentation                          
```

---

## About the Author

I am a Healthcare and Clinical Data Analyst with a background in Molecular Genetics. I work at the point where clinical knowledge and data analytics meet, which means I do not just clean data and build dashboards. I understand what the numbers mean in a health context and why getting them right matters.

I am open to healthcare analytics roles, health tech positions, and interesting collaborations. If you are working on something in this space and want a second pair of eyes or a full analytical partner, feel free to reach out.

- [LinkedIn](https://www.linkedin.com/in/muoneke-nwamba)
- [GitHub](https://github.com/Neksperfect)
- donmoen.devdas@yahoo.com

---

*Technical assessment completed for Platos Health.*


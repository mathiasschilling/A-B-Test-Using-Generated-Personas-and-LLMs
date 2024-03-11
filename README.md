# A/B Test of Job Descriptions Using Personas and LLMs

## Project Description

In the evolving landscape of talent acquisition and job design, the utilization of advanced computational techniques, including Large Language Models (LLMs) and persona-based evaluation methods, represents a cutting-edge approach to optimizing job descriptions for various roles. This innovative methodology involves the creation of detailed personas, which encapsulate a wide range of candidate profiles, preferences, and competencies. These personas are then used in combination with LLMs to assess and vote on job positions, determining which descriptions are more effective in attracting the right talent.

## Creating Personas

To create 100 personas of students from 5 fields of study (machine technology, electronics engineering, data science, information technology, and industrial engineering), we follow these steps:

- Assign each student a name.
- Define their field of study (`study`) and associated skills (`skills`).
- Link professional interests (`professional_interests`) to their fields of study and skills.
- Introduce variability in skills and interests to create diverse personas.
- Randomize private interests (`private_interests`) and social skills (`social_skills`) for each persona.

This approach ensures the creation of unique personas for our A/B testing.

## Job Descriptions

Enter your job descriptions below:

- `job_description_A`: Control job description (currently used).
- `job_description_B`: New phrasing of the job position for comparison.

## Prompting

To verify the setup:

1. Create a first prompt and ensure correctness.
2. Test for the correct output using the OpenAI API.

In case no OpenAI API is found, create a `config.py` file with your OpenAI private API key:

```python
api_key = 'your_private_api_key_from_openai'
```

## Create Survey Based on Personas

We will gather votes from every persona in the dataset (100 in total). This process may take some time.

## Illustrate Votes by Studies

Analyze how different fields of study voted to identify any differences or trends.

## Evaluation of the A/B-Test

We use the proportions_ztest from the statsmodels package for the A/B test to determine if job description B is significantly better than A based on total votes.

### Interpretation of the Results

Z-statistic and p-value are key metrics for understanding the statistical significance of the test results, with a p-value less than 0.05 indicating a statistically significant difference.


## Additional Remarks

The A/B test can be run multiple times with the same personas to identify vote distributions for each persona, enhancing the depth of analysis.








# A/B test of job offers using personas and LLM's

## Project description


## Creating personas


## Job descriptions
The following are two job descriptions for a "C++ firmware developer" position at a tech company. The first one (`job_description_A`) is the original one that is currently used by the company. The second one (`job_description_B`) is a modified one that uses more engaging and inclusive language.

`job_description_A`:

C++ Firmware Developer for Embedded Systems (m/f/d) 80-100%

Your Responsibilities:
You will develop embedded software for our innovative and modular microcontroller platform used in our instruments.
You will work across technologies to develop firmware components and products in collaboration with colleagues from hardware and other departments.
You will participate in all project phases, from requirements gathering to the release for mass production.

Your Profile:
You have completed a Bachelor's or Master's degree in Electrical Engineering or Computer Science.
Your track record includes solid knowledge and several years of experience in object-oriented programming.
You are characterized by your proactive and curious work attitude, as well as your enthusiasm for complex technical challenges.
You have good proficiency in both German and English.

What We Offer:
Highly diverse and responsible projects in a dynamic and future-oriented high-tech company.
Integration into an environment filled with experience and passion.
Work in international project teams.
Top-notch infrastructure, including state-of-the-art tools, fitness and relaxation rooms, and a staff restaurant.
Opportunities for internal and external training.
Attractive social benefits.

`job_description_B`:

C++ Firmware Developer for Embedded Systems (m/f/d) 80-100%

Your Responsibilities:
Engage in the agile development of embedded software for our cutting-edge microcontroller platform, driving innovation in our instruments.
Collaborate in a fast-paced environment to create firmware components and products, leveraging cross-functional teamwork with hardware and other departments.
Be an active player throughout the project lifecycle, embracing adaptability from initial concept to production readiness, in our quest to continuously deliver excellence.

Your Profile:
Whether you hold a degree in Electrical Engineering, Computer Science, or possess equivalent practical experience, we value diverse educational backgrounds.
A foundation in object-oriented programming is essential, but your passion for technology, problem-solving skills, and eagerness to learn are what truly set you apart.
Your proactive attitude, curiosity, and love for tackling complex challenges will make you a perfect fit. Being a team player is key.
Proficiency in German and English is needed to collaborate effectively in our international teams.

What We Offer:
Work on highly diverse and challenging projects in an agile and forward-thinking high-tech company.
Be part of an enthusiastic environment that values experience and passion for technology.
Collaborate with international teams in a fast-paced setting that encourages quick learning and agile responses to change.
Enjoy access to top-notch facilities, including the latest tech tools, fitness and relaxation areas, and a company restaurant, all designed to support your well-being.
Take advantage of extensive opportunities for both internal and external training to help you grow professionally.
Benefit from attractive social benefits and a culture that supports work-life balance and personal development.




# Project Title: A/B Test of Job Offers Using Personas and LLMs

## Table of Contents
- [Introduction and Project Description](#introduction-and-project-description)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Creating Personas](#creating-personas)
  - [Setting Up Job Descriptions](#setting-up-job-descriptions)
  - [Prompting and Testing with LLMs](#prompting-and-testing-with-llms)
  - [Creating a Survey](#creating-a-survey)
  - [Illustrating Votes by Studies](#illustrating-votes-by-studies)
- [A/B Testing](#ab-testing)
  - [Evaluation Methodology](#evaluation-methodology)
  - [Interpretation of Results](#interpretation-of-results)
- [License](#license)
- [Author](#author)

## Introduction and Project Description
In the evolving landscape of talent acquisition and job design, the utilization of advanced computational techniques, including Large Language Models (LLMs) and persona-based evaluation methods, allows for new approaches to optimizing job descriptions for various roles. This innovative methodology involves the creation of detailed personas, which encapsulate a wide range of candidate profiles, preferences, and competencies. These personas are then used in combinations with LLMs to assess and vote on job positions, determining which descriptions are more effective in attracting the right talent.

## Getting Started

### Prerequisites

Before you can run this project, you'll need to have the following installed on your system:

- Python 3.9.12: Ensure you have Python version 3.9.12 installed. You can download it from [python.org](https://www.python.org/downloads/release/python-3912/) or use a version manager to install this specific version.

Additionally, you'll need an API key from OpenAI to use their models:

- OpenAI API Key: Obtain an API key by creating an account at [OpenAI](https://openai.com/api/) and following their instructions to generate an API key.

### Installation

1. **Clone the Repository:**

   Start by cloning this project to your local machine. You can do this by running the following command in your terminal:

   ```bash
   git clone https://github.com/your-repository-url-here.git
   ```
   
2. **Create a Virtual Environment (Optional):**

It's recommended to create a virtual environment to manage the dependencies for the project. You can create one using `venv` by running:

```bash
python3 -m venv env
source env/bin/activate  # On Windows, use `env\Scripts\activate`
```

3. **Install Required Packages:**

Install all the required packages using the pip command. Make sure you are in the project directory and run:

```bash
pip install pandas numpy requests matplotlib statsmodels
```

4. **Set Up OpenAI API Key:**

Create a file named `config.py` in the root of the project directory. Add your OpenAI API key to this file as shown below:

```python
api_key = 'your_private_api_key_from_openai'
```

Replace 'your_private_api_key_from_openai' with the actual API key you obtained from OpenAI.

5. **Verification:**

Ensure that all installations are correct and packages are working as expected. You can run a simple Python script to check if the packages are imported correctly.

Once you've completed these steps, you're ready to proceed with the usage of the project, detailed in the following sections.


## Usage

### Creating Personas
To create realistic and diverse personas, we use a combination of data sources, such as census data, academic records, and online surveys. We then apply natural language processing and clustering techniques to generate 100 personas of students from 5 fields of studies: machine technology, electronics engineering, data science, information technology, and industrial engineering. Each persona has the following attributes:

- `name`: Randomly created names.
- `study`: One of the five fields of studies mentioned above.
- `skills`: A list of skills that are relevant to the chosen field of study, such as programming languages, software tools, mathematical concepts, etc. The skills are randomly selected from a predefined pool of skills for each field of study, with some variation to allow for different levels of proficiency and specialization.
- `professional_interests`: A list of topics or domains that the persona is interested in pursuing as a career, such as artificial intelligence, robotics, cybersecurity, etc. The professional interests are tied do the fields of study.
- `private_interests`: A list of hobbies or activities that the persona enjoys doing in their spare time, such as sports, music, gaming, reading, etc. The private interests are randomly selected from a general pool of interests that are not related to the field of study or the professional interests.
- `social_skills`: A list of social skills. The social skills are randomly assigned to each persona.

The initial persona traits, skills and interests can easily be adjusted and expanded.

In function `get_persona(idx)`, where `idx` is the index/persona, we create the persona based on the traits, skills and interests associated in the data frame.

### Setting Up Job Descriptions
The cornerstone of this project is the comparison of different job descriptions to understand which are more effective in attracting the right candidates. Begin by drafting two versions of job descriptions for the same role: `job_description_A` as the control version (the current job description used) and `job_description_B` as the experimental version (with potentially more engaging and inclusive language, clearer role responsibilities, or other modifications). These descriptions should be reflective of the role's requirements and the organization's culture. The effectiveness of each description is later assessed through A/B testing, leveraging the unique perspectives of our generated personas.

Example job descriptions are defined in the jupyter notebook.

### Prompting and Testing with LLMs
Once personas and job descriptions are established, the next step involves interacting with LLMs to simulate how each persona would react to the job descriptions. This involves crafting prompts that summarize the job descriptions and the persona's profile, querying the LLM for its preference or reaction towards the descriptions.


### Creating a Survey

To systematically capture the preferences of our personas for job description A vs. job description B, we create a survey. This survey is designed to gather the votes of each persona on which job description they find more appealing or suitable. Implementing this survey involves scripting a process where each persona, represented by their profile data, is 'asked' to choose between the two descriptions. The survey is automated to process all personas sequentially, recording their preferences and preparing the data for statistical analysis to determine the more effective job description.

### Illustrating Votes by Studies

After collecting votes from the personas on their preferred job descriptions, it's important to visualize and analyze these preferences across different fields of study. This step involves creating graphical representations, such as bar charts or pie charts, to illustrate how personas from different academic backgrounds (e.g., machine technology, electronics engineering, data science) voted. 

![Illustration of the votes by fields of study of a demo survey.](demo_survey.png)

Such illustrations can reveal trends and patterns, highlighting which job descriptions resonate more with candidates from specific fields. This analysis is crucial for understanding how to tailor job descriptions to attract diverse talents effectively.



## A/B Testing

### Evaluation Methodology
The evaluation methodology of the A/B testing relies on statistical analysis to measure the effectiveness of the two job description versions. Utilizing the `proportions_ztest` from the `statsmodels` package, this process compares the proportion of positive responses each job description receives from the personas. By setting a controlled environment where other variables are kept constant, this approach ensures that the observed differences in preferences are attributable to the variations in the job descriptions. This methodology is critical for making informed decisions based on empirical data rather than intuition.

### Interpretation of Results

**1. Z-statistic:**

The Z-statistic represents the distance between the observed difference in proportions and the null hypothesis value (typically, the null hypothesis states that there is no difference between the two proportions), expressed in the number of standard deviations. A Z-statistic of 0 indicates that the observed difference is exactly the same as the null hypothesis value.

**2. p-value:**

The p-value helps us determine whether the observed differences are statistically significant. It represents the probability of obtaining test results at least as extreme as the ones observed during the test, assuming that the null hypothesis is true. In the context of an A/B test, a p-value less than 0.05 (common threshold) suggests that there is a statistically significant difference in preferences between the two versions tested, leading us to reject the null hypothesis (meaning the second job description is better).

## License

This project is made available under the terms of the MIT License. This means everyone is free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, provided they do so under the same license and give appropriate credit to the original author(s) of this project by referencing it in their work.

While not required, if you find this project helpful and wish to express your appreciation, I would be grateful for a coffee donation. Donations can be made to the following Ethereum/Polygon wallet address: `0x9F74DbeeA147D6DcF5Da550EDa3DDa0FF92e7daA`. Your support is greatly appreciated.

## How to Cite This Project

If you utilize this project in your research, development work, or in any other capacity, please consider citing it as follows:

Schilling, M. (2024). A/B Test of Job Descriptions Using Personas and LLMs. GitHub. https://github.com/mathiasschilling/AB-test-of-job-descriptions-using-personas-and-LLMs

## Author

This project was created by Mathias Schilling, a passionate algorithm developer and data scientist with a keen interest in applying technology to solve real-world problems. With a background in systems engineering, Mathias brings a unique perspective to the intersection of data science, applied machine learning, RAG and data-driven analysis and modeling. This project reflects his commitment to innovative approaches in optimizing recruitment processes and enhancing job matching through the power of Large Language Models (LLMs) and data-driven insights. 
For any inquiries or collaborations, feel free to connect on [LinkedIn](https://ch.linkedin.com/in/mathias-schilling-3a9b1210b).


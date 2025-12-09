---
title: import test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---


# Career Pathways

> Ready to use this data? See the Career Pathways [reference documentation](/apis/career-pathways) to get started.

## Description

The Lightcast Career Pathways API includes calls to explore career advancement pathways for a selected occupation and also highlight the skills needed to advance from one job to the next. These data elements are powered by separate models – one that provides Career Pathways (i.e., next step and feeder occupations) and another that provides information on the skills gap between any pair of occupations.

### Methodology:

Lightcast develops Career Pathways in the Lightcast Occupation Taxonomy at the LOT Specialized Occupation and LOT Occupation levels and the latest O*NET-SOC Taxonomy at the 6-digit SOC and 8-digit ONET Occupation levels. Pathways are developed as attributes that are specific to an occupation, and as such are expected to apply across geographies within a country.

Next step and feeder occupations are those that represent logical transitions out of / into a selected occupation based on similar skill, education, and experience requirements. Next step occupations are classified into four categories:

* _Advancement jobs_ that pay more and are within the same occupation group as the selected occupation.
* _Lateral advancement jobs_ that pay more but require transition to a new occupation group.
* _Similar jobs_ that pay a comparable salary and are within the same occupation group.
* _Lateral transition jobs_ that pay a comparable salary but require transition to a new occupation group.

### Skill Gap:

Lightcast Career Pathways are also accompanied by data on the skills needed to enable each transition. This is powered by a skills gap model that provides the skills needed to move from a source occupation to a destination occupation, along with a score that indicates the relative importance of the skill in making the transition. Skill gap is directional, i.e. the skills needed to move from A -> B could be different from the skills needed to go from B -> A. For any given source-destination occupation pair, the gap skills are identified as all of the defining and necessary skills for the destination occupation that are more important to the destination than they are to the source. These gap skills are scored and ranked using an 'importance score'. The score is calculated as a weighted combination of how large the gap is in the skill's similarity of the destination compared to the source, and the skill's salary. Thus, the skills recommended by the model are the ones that are the most important to learn and provide the greatest salary boost.

### Data Sources:

Lightcast Career Pathways by Occupation use the following data sources:

1. _Occupation to Occupation Similarity Scores:_ Similarities in skill requirements across occupations are captured by means of a Similarity Score.
2. _Requirement Levels and Job Zones:_ Lightcast Occupations (LOT) and Specialized Occupations (LOT) are classified into one of six categories based on levels of education, experience, and training required to qualify for the occupation:
   * Requirement Level 1: Roles with minimal training requirements.
   * Requirement Level 2: Roles with formal training requirements of less than 2 years.
   * Requirement Level 3: Roles with 2 year specialized degree requirement or a mix of sub-BA and BA requirements.
   * Requirement Level 4: Entry level BA roles.
   * Requirement Level 5: Advanced BA roles.
   * Requirement Level 6: Graduate and professional roles.

O_NET occupations are similarly classified into five job zones based on the levels of education, experience, and training required to qualify for that occupation. Definitions are available on the O_NET website: [https://www.onetonline.org/help/online/zones](https://www.onetonline.org/help/online/zones).

3. _Salary by Occupation:_ Average annual advertised salary in the last 12 months for each occupation.
4. _Specialized Training Requirements:_ Occupations that typically require a license or specialized training are identified in the Lightcast Occupation Taxonomy. The training requirements for these Lightcast Occupations are crosswalked to Specialized Occupations as well as SOC and O*NET Occupations.
5. _Occupation Taxonomy Elements:_ The algorithm uses two primary taxonomic levels from the Lightcast Occupation Taxonomy (LOT) and the O*NET-SOC Occupation Taxonomy as the relational context for producing detailed pathways. These levels are:
   * Occupation Group: These are Occupation Groups in LOT and 4-digit SOC Occupations in the O*NET-SOC Taxonomy.
   * Career Area: These are Career Areas in LOT and 2-digit SOC Occupations or Major Groups in the O*NET-SOC Taxonomy.

## Use Cases

#### Questions answered by this dataset:

* What are common advancement jobs for a given occupation?
* What are common feeder jobs for a given occupation?
* What are the most valuable skills needed to advance from one job to another?

## Metrics

* None

## Filters

* Occupation id (LOT, SOC, O*NET)
* Categories (Advancement, Lateral Advancement, Similar, Lateral Transition)

 +++

title = "Python crash course, Module 2 'Distributed Systems'"
description = "Introduction to the course"
outputs = ["Reveal"]
aliases = [
    "/intro/"
]

+++

{{% import path="reusable/header-course.md" %}}

---

# Teachers

## Module 1 (i.e., theory)

**teacher:** {{<ao>}}, full professor

**email:** {{<ao-address>}}

## Module 2 (i.e., practice)

**teacher:** {{<gc>}}, junior assistant professor (RTD-A)

**email:** {{<gc-address>}}

**tutor:** {{<mm>}}, PhD student

**email:** {{<mm-address>}}

<!-- **office hours** dynamic, email the teacher for an appointment -->

---

## Virtuale

### {{<vle_url>}} (old link!)  

Students _must_ enroll

- listen for announcements on the {{<forum_news>}}  
- ask for help or provide feedback on the {{<forum_general>}} 

---

## What is {{<course_name>}} about? (pt. 1)

- Put it simply, it is about __learning python__ and __producing good quality software products__
    + not only writing code, but also 
        1. _understanding_ the _requirements_, 
        2. _designing_ the _product_, 
        3. _testing_ it, 
        4. _deploying_ it, 
        5. and _maintaining_ it

- In particular, nowadays, software engineering must also deal with:
    + __distribution__, i.e. multiple software components interconnected over the _Internet_
    + __artificial intelligence__ (not in this course), i.e. software components that may exhibit _human-like_ capabilities to some extent
        - e.g. understanding natural language, recognizing objects, making decisions, learning from data, etc. 

---

## What is {{<course_name>}} about? (pt. 2)

- At the end of the course...
    + ... you shall have a clear understanding on the __whole process__ of software engineering
    + ... you should be able to _set up_ and _design_ a __python software project__
    + ... you should be able to _reason_ about the __quality__ of a software project
    + ... you should have a clear understanding of brings __cost__ or __value__ in a software project

- To reach that goal, we shall follow a __learn-by-doing__ approach

---

## Why Python?

- In the past years, we used __Java__ for this course
- We switched to __Python__ for several reasons:
    <!--+ we cannot take for granted that you already know Java
    + students from our Bachelor's in Computer Science know Java but students from other Bachelor's may not-->
    + Python is one of the most _popular_ programming languages
    + Python is arguably _easy_ to learn and _read_
    + Python is _faster_ for prototyping than Java
    + This semester you will also use Python in the __Machine Learning__ course

---

## Exam: overview (pt. 1)

- The exam consists of a __project work__ to be _produced_ and _presented_ by students 

- The project work consists of 
    1. the __source code__ of a _software artifact_ and 
    2. a __textual report__ describing the _design_ and _development processes_ of the artifact itself

- The __report is more important than the source code__

- The project work can be done _individually_ or in _groups_ of __up to 3 students__ -- __4 students__ in exceptional and wee-motivated cases

---

## Exam: overview (pt. 2)

- Students are encouraged to _propose_ project works themes/topics/concepts
    + we may help in refining initial proposals
    + usually students propose project works that are _too ambitious_ (e.g., too many features for the time available)
    + considering that the course is __6 CFU__, we suggest to propose project works that can be _completed_ in __about 90 hours__ of work (per student)

- We incentivise students to _complete_ their project work __as soon as possible__ 
    + better if within _the next exam session_ (i.e., we will positively consider early submissions until the beginning of the next semester)
    + possibly within _the same academic year_ (i.e., next year that could be different rules, maybe more strict)

---

## Exam: workflow (pt. 1)

1. **Proposal**: students _propose_ a project theme/topic/concept on {{<vle>}}
    - in case of group project, the group members should be _declared_ here

2. **Approval**: the teacher will provide feedback and possibly suggest changes/strategies or set requirements

3. **Repository creation**: students _create a GitHub repository_ and _share it_ with the teacher
    - granting _admin_ access to the teachers' GitHub accounts (username: [`gciatto`](https://github.com/gciatto), [`MatteoMagnini`](https://github.com/MatteoMagnini))

4. **Development**: students _develop_ the software artifact and _write_ the report
    - the report should be written in [Latex](https://www.latex-project.org/)
    - the report should be written in _English_
    - you can use the [Latex template](https://github.com/pikalab-unibo/report-template)

---

## Exam: workflow (pt. 2)

5. **Submission**: students _submit_ the repository URL on {{<vle>}} and ask an _appointment_ for the discussion
    - the final __pdf__ version of the report must be uploaded as well
    - submission is _not retractable_
    - at this point we will read the report and evaluate the project work
    <!--- we can __ask for changes__ to the report or the software artifact-->
    - or immediately _approve_ the project for the discussion

6. **Discussion**: students _present_ and _discuss_ their project work with the teacher
    - appointments may be scheduled in any moment of the academic year taking the teachers' availability into account
    - the discussion will be held either _in English_ or _in Italian_
    - remote discussion may be possible via [Microsoft Teams](https://teams.microsoft.com/), in case of well-justified needs
    - the discussion will include __all the members__ of the group

---

## Exam: the software artifact

- The software artifact must be a _working_ piece of software
    + it must be _runnable_ and _testable_ on the teacher's machine
    > _"it works on my machine"_ is not a valid excuse
    + it must be _documented_ in the report

- The software artifact can be developed in _any programming language_ of choice
    + we _recommend_ using __Python__

- The software artifact is mostly aimed at demonstrating students' _understanding_ of the many aspects of __Distributed Systems__,
so that's what we will _mostly_ evaluate
    + e.g., analysing requirements, modelling a solution, designing interfaces, working features, corner cases, failures handling, writing tests, managing dependencies, automating builds, tracking development, versioning, etc.

- Exploitation of Git, GitHub, and version control is __important__ to facilitate your own work

---

## Exam: the report

> The report is more important than the software artifact

- The report must be a document describing the __design__ and __development processes__ of the software artifact
    + must speculate on the aspects related to __Distributed Systems__

- The report is the _entry point for evaluating_ the project work
    + it should detail _what has been done_ and _what has not been done_ (and _why_) ...
    + ... w.r.t. __some aspects__ of __Distributed Systems__ presented in the course

- Templates and guidelines for the report will be provided on {{<vle>}}

---

<!--
## Exam (the evaluation)

- Project work is _evaluated_ __once per group__
    1. an _overall mark_ is assigned to the project work, hence to the group
    2. _individual marks_ are then adjusted based on the __individual contributions__ to the project work

- Roughly speaking the evaluation of the project work will be based on the following aspects:
    + the _quality_ of the report and the presentation
    + the _precision_ of requirements elicitation and analysis
    + the _clarity_ of the design _documentation_
    + the _presence_ of tests and the _meaningfulness_ of the testing process
    + the _correct exploitation_ of 
        1. version control systems
        2. build automation systems
        3. continuous integration systems
    + the _adequate_ management of dependencies, versions, and licenses

- Extra points may be granted in case of (details on {{<vle>}}):
    + _early_ submission
    + _completeness_ of the software artifact
    + _quality_ of the software artifact

---

## Exam (examples of project works)

1. A web, mobile, or desktop __App__, possibly involving some _remote service_
    + e.g., a simple video game (involving online multiplayer) 
    + e.g., a calculator (involving a remote computation for advanced operations)
    + e.g., an instant messaging application
    + e.g., a note-taking, to-do list, calendar app (involving cloud storage)
    + e.g., a weather forecast (relying on pre-existing forecasting services)
    + e.g., a news aggregator (possibly scraping news from the web)
    <!-- + e.g., a social network client (possibily aggregating data from multiple sources) -->

<!--
2. A __startup__ _idea_, possibly involving some _remote service_
    + e.g., booking and managing appointments for professionals
    + e.g., general all-you-can-eat menus for restaurants
    + e.g., food delivery service
    + e.g., a platform for sharing and renting cars, bikes, rooms, etc.

3. A _toolkit_ supporting some (_data?_) __processing__ or __anlysis activity__ (with an _output_)
    + e.g., data analysis on social media, or GitHub
    + e.g., a tool for systematic literature reviews
    + e.g., a tool for automated document difference (possibly relying on third-party Web services)
    + e.g., a tool generating datasets via LLM

---
-->

<!--
## Example proposal 1

#### An analysis of developer distress on social media 

* *Type*: mixed
* *Group size*: 2-4

This activity consists in the analysis (via scraping / API) of social media posts that indicate developers' distress,
and on a classification of their origin.
Sources may include Twitter, Reddit, Stack Overlow, etc.

*Notes*:
* It might benefit of pre-existing skills in sentiment analysis

---

## Example proposal 2

#### How are successful GitHub workflows organized?

* *Type*: mixed
* *Group size*: 2-4

This activity consists in the analysis (via API) of some interesting relationships that could be found on GitHub,
with the goal of investigating developer's habits and their evolution with time.

Some questions of interests may be:
* do the developer count relate to the branch count?
* do the presence of merge commits relate to the "success" of the project?

*Notes*:
* Identifying developers univocally may not be so easy
* More metrics could be devised
* Project success should be measured somehow but it is not trivial at all

---

## Example proposal 3

#### Private clouds with Kubernetes: a complete setup

* *Type*: project
* *Group size*: 1-2

This activity consists in the construction of a working private cloud based on Kubernetes.
Required features:
* Resilience to the loss of a master node (multi-master)
* Ability to run services (long-lived processes) or tasks (short-lived processes)
* Resource control and allocation via RBAC

*Notes*:
* Compute servers will be provided by the teacher
* Setup details should be collected into a guide
* Previous experience with Kubernetes and containerization is helpful

---

## Example proposal 4

#### Automated document difference

* *Type*: project
* *Group size*: 1-2

The goal of this project is to build a library leveraging the web API of [Draftable](https://draftable.com/)
to produce differential documents.
The software can be developed in any language of choice,
and must feature appropriate automation (build) and get published on official distribution channels.

The library should be exercised with a GitHub action.

*Notes*:
* The API key for the Draftable service will be provided by the teacher
* The language should be agreed with the teacher
    * Python, Java, Scala, Kotlin, Rust, and Ruby are all valid picks, other should be discussed

---

## Example proposal 5

#### A tool to support systematic literature reviews

* *Type*: project
* *Group size*: 1-2

The goal of this project is to build a software that queries multiple sources in the literature
(Google Scholar, Pubmed, Scopus, Web of Science, Arxiv...)
with a specific query, supporting the scientific investigation of existing results.
The software can be developed in any language of choice,
and must feature appropriate automation (build) and get published on official distribution channels.

*Notes*:
* The language should be agreed with the teacher
    * Python, Java, Scala, Kotlin, Rust, and Ruby are all valid picks, other should be discussed

---
-->

## Technical Requirements

- An account on [GitHub](https://github.com) (create one if missing)
    + possibly, __based on your university email address__
        * if you already have a GitHub account, please add it as the secondary email address 
    + optionally, __with a profile picture__ showing your face or a recognizable avatar
    + possibly, with a __professional username__ (e.g., `john-doe` instead of `johnny-the-king`)

- A working installation of [Python](https://www.python.org/)
    + possibly version `3.11.x`

- A working installation of [Git](https://git-scm.com/)
    + if you need a GUI, you may choose 
        1. [GitHub Desktop](https://desktop.github.com/) 
        2. [SourceTree](https://www.sourcetreeapp.com/)
        3. [GitKraken](https://www.gitkraken.com/)

- A working installation of [Visual Studio Code](https://code.visualstudio.com/)

- \[Recommended\] A working installation of [PyCharm](https://www.jetbrains.com/pycharm/)
    + the community edition is free, and it's enough

--- 

# Module 2 remarks

- Lectures are recorded by default
    + recordings will be available on {{<vle>}}
    + access to recordings is by-request only (email the teacher)

- Slides and other materials are available on {{<vle>}}
    + they are produced along the way, so they may not be available in advance
    + also, please re-download / re-load them before each class

---

## Module contents and action plan

0. [Course Overview](..)
1. [Preliminary notions for Software Development](intro)
2. [Introduction to the Python Language](language)
3. [How to manage a Python Project](python-project)
4. [A Python Project Example](example)
5. [QA, testing, TDD, reproducibility and replicability](qa-tdd)

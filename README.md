# 🎓 EdTech Courses Analysis – Power BI Project 
## Project at a Glance  

| **What I Did** | **Why It Matters** | **How I Did It** | **Business Outcomes** |
|----------------|--------------------|------------------|-----------------------|
| Built an interactive Power BI dashboard analyzing 5,000+ EdTech courses across platforms. | Platforms need to know what courses, formats, and accessibility features drive engagement. | Power Query (cleaning, transformations), DAX (aggregations, rankings), visuals (slicers, drilldowns, word cloud). | Clear actions for Product (launch mix), Marketing (localization), Content Strategy (skills & instructors), and Ops (accessibility ROI). |


## Introduction  
The EdTech industry is growing faster than ever, with thousands of online courses competing for learners’ attention. For a platform, it’s not enough to just host courses — you need to know **which courses resonate, what skills are in demand, and how factors like language or duration affect enrollments**.  

In this project, I took on the role of a data analyst at an EdTech company. My goal was simple but powerful:  

<ul>
  <li>Identify which courses and formats drive the most engagement.</li>
  <li>Understand whether subtitles, duration, and language really influence learner decisions.</li>
  <li>Highlight top skills and instructors that deserve investment.</li>
</ul>  

To do this, I built an <b>interactive Power BI dashboard</b> from a raw dataset containing thousands of online courses across platforms like Coursera, FutureLearn, and Simplilearn. My objective wasn’t just “pretty charts”—it was to surface decisions the team could take next month: what to launch, where to localize, whom to feature, and whether accessibility spend pays off.

---

## Data Journey  

### 1. Understanding & Cleaning the Data  
I started in <b>Power Query</b>, where I profiled the dataset and ensured quality:  

<ul>
  <li>Removed duplicates, blanks, and error rows.</li>
  <li>Dropped completely empty columns.</li>
  <li>Converted text-based ratings like <i>“4.8 stars”</i> into numeric values.</li>
  <li>Standardized course durations, which were written in mixed formats (hours, weeks, months).</li>
</ul>  

This step was critical — clean, consistent data builds the foundation for any trustworthy insight.  

### 2. Framing the Right Business Questions  
Instead of just looking at columns, I asked myself: <i>How can these fields answer real business questions?</i>  

<ul>
  <li><b>Category/Sub-Category</b> → Which subjects attract the most learners?</li>
  <li><b>Course Type</b> → Do learners prefer certifications, projects, or full specializations?</li>
  <li><b>Languages & Subtitles</b> → Does accessibility improve reach and engagement?</li>
  <li><b>Skills & Instructors</b> → Where should the company invest for the highest learner impact?</li>
</ul>  

By framing data this way, I turned attributes into <b>business levers</b> that a product or strategy team would care about.  

---
<!-- =========================
     3) HOW I WORKED
========================= -->
<section id="how-i-worked">
  <h2>3) How I worked (Power Query &rarr; Model &rarr; Visuals)</h2>

  <!-- A) DATA PREP -->
  <h3>A) Data preparation (Power Query)</h3>
  <ul>
    <li>Profiled data quality to see valid / error / blank distributions.</li>
    <li>Removed errors, duplicates, and blank rows in bulk; dropped 100% empty columns.</li>
    <li>Parsed ratings from text (<em>&ldquo;4.8 stars&rdquo; &rarr; 4.8</em>) using <strong>Text Before Delimiter</strong>, then enforced numeric types.</li>
    <li>Standardized course duration so comparisons weren&rsquo;t biased by mixed units.</li>
    <li>Ensured key slicer fields (e.g., <strong>Category</strong>) contained no nulls.</li>
  </ul>
  <p>
    <em><strong>Business lens:</strong> Clean, consistent columns prevent false trends. Enforcing non-null slicers ensures decision-makers can reliably filter by the dimensions they care about (like category) without gaps.</em>
  </p>

  <!-- B) MODELING CUES -->
  <h3>B) Modeling cues</h3>
  <ul>
    <li>Used a single-table analysis for this snapshot with focused measures: <em>Avg Views</em>, <em>Avg Rating</em>, <em>Courses Count</em>, and <em>Instructor Rank</em>.</li>
    <li>Designed slicers and drill paths around the <strong>category &rarr; subcategory &rarr; language</strong> storyline the business requested.</li>
  </ul>

  <!-- C) VISUAL DESIGN -->
  <h3>C) Visual design &amp; interactions</h3>
  <ul>
    <li><strong>Category slicer</strong> as the global control (everything updates by subject).</li>
    <li><strong>Course Type &times; Category</strong> (stacked bar + ribbon) to see format tilt per subject.</li>
    <li><strong>Avg Views by Subcategory &rarr; Language</strong> (drill down) to localize marketing.</li>
    <li><strong>Language distribution</strong> to size localization opportunities.</li>
    <li><strong>Skills word cloud</strong> (custom visual) to spot content themes (with a data-prep fix so compound skills don&rsquo;t overcount).</li>
    <li><strong>Top-3 instructors by rating</strong> for partnership and storefront decisions.</li>
    <li><strong>Duration vs Views</strong> and <strong>Subtitles vs Views</strong> to test design and accessibility hypotheses.</li>
  </ul>
  <p>
    <em><strong>Business lens:</strong> Each visual answers a &ldquo;so-what&rdquo; that maps to a decision&mdash;launch mix, ad targeting, instructor promotion, or subtitle budget.</em>
  </p>
</section>

<!-- =========================
     4) WHAT I FOUND
========================= -->
<section id="findings">
  <h2>4) What I found (and why it matters)</h2>

  <!-- A -->
  <article>
    <h3>A. Format strategy (Course Type &times; Category)</h3>
    <ul>
      <li>Some subjects skew toward <strong>specializations</strong>; others convert better with <strong>short projects</strong> or <strong>professional certificates</strong>.</li>
      <li><strong>Decision:</strong> Align the release calendar to each subject&rsquo;s winning format to lift conversions.</li>
    </ul>
  </article>

  <!-- B -->
  <article>
    <h3>B. Localization focus (Avg Views by Subcategory &rarr; Language)</h3>
    <ul>
      <li>Engagement shifts meaningfully at the <strong>language</strong> level once you drill down.</li>
      <li><strong>Decision:</strong> Localize the top 1&ndash;2 subcategories per subject first (fast ROI) instead of broad translation.</li>
    </ul>
  </article>

  <!-- C -->
  <article>
    <h3>C. Skill themes (Word Cloud)</h3>
    <ul>
      <li>Recurrent skills reveal <strong>content gaps</strong> the catalog can fill for quick wins.</li>
      <li>I fixed a common pitfall by cleaning spaces in compound skills, so the cloud ranks true skills (e.g., <code>Data_Visualization</code> instead of inflating the word &ldquo;Data&rdquo;).</li>
      <li><strong>Decision:</strong> Prioritize development on the top skill clusters visible in current high-view subjects.</li>
    </ul>
  </article>

  <!-- D -->
  <article>
    <h3>D. Accessibility ROI (Subtitles vs Views)</h3>
    <ul>
      <li>The dashboard explores whether courses with <strong>more subtitle languages</strong> see higher views.</li>
      <li><strong>Decision:</strong> Run a controlled rollout&mdash;add subtitles for high-intent geos in one subject and measure the lift before scaling.</li>
    </ul>
  </article>

  <!-- E -->
  <article>
    <h3>E. Instructional design (Duration vs Views)</h3>
    <ul>
      <li>Tested whether <strong>shorter courses</strong> pull more first-time enrollments in certain subjects.</li>
      <li><strong>Decision:</strong> A/B test <em>micro-course</em> pilots where long form underperforms.</li>
    </ul>
  </article>
</section>

## Dashboard Highlights  

<ul>
  <li><b>Category & Course Type Analysis</b> → Showed which categories lean heavily toward specific course types, guiding product launches.</li>
  <li><b>Average Views (Category → Sub-Category → Language)</b> → Revealed engagement shifts as we drilled deeper, helping marketing teams localize campaigns.</li>
  <li><b>Language Distribution</b> → Identified which languages dominate the platform, valuable for global expansion.</li>
  <li><b>Skills Word Cloud</b> → Highlighted trending skills, so course development could align with real market demand.</li>
  <li><b>Top Instructors (Top 3 by Rating)</b> → Spotlighted high-performing educators worth promoting or partnering with.</li>
  <li><b>Duration vs. Engagement</b> → Tested whether course length impacts enrollments, informing instructional design.</li>
  <li><b>Subtitles Impact</b> → Explored if multilingual subtitles correlated with higher purchases — a direct link between accessibility and revenue.</li>
</ul>  

Each of these visuals answered a <i>“so what?”</i> question — not just displaying numbers, but shaping <b>strategic decisions</b>.  

---

## Business Impact  

This dashboard goes beyond pretty visuals. It’s a <b>decision-support tool</b>:  

<ul>
  <li><b>Product Managers</b> can see what formats and categories drive demand, and prioritize new launches accordingly.</li>
  <li><b>Marketing Teams</b> can refine targeting strategies by language and learner behavior.</li>
  <li><b>Content Strategists</b> can double down on trending skills and successful instructors.</li>
  <li><b>Operations</b> can measure the ROI of subtitles and accessibility investments.</li>
</ul>  

In short, it turns raw course data into <b>clear, actionable strategy</b> — helping optimize portfolios, grow engagement, and improve returns.  

---

**Business thinking**  
<ul>
  <li>Asking the right questions that tie analysis to strategy.</li>
  <li>Viewing data as a story that guides action.</li>
  <li>Translating insights into recommendations for product, marketing, and operations.</li>
</ul>  
---

## Conclusion  

The <b>EdTech Courses Analysis</b> project reinforced something I believe strongly:  
A data analyst’s job isn’t just to build dashboards — it’s to <b>tell a story that moves the business forward</b>.  

By combining technical expertise with business understanding, I turned scattered course records into insights that guide product launches, marketing campaigns, and learner success.  
 



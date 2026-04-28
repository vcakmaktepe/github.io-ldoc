---
layout: default
---

<style>
  body {
    background: #f7f5ef;
    color: #1f2933;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
    line-height: 1.65;
  }

  .page-wrap {
    max-width: 1040px;
    margin: 0 auto;
    padding: 2rem 1rem 4rem;
  }

  .project-header {
    padding: 1.5rem 0 2rem;
    border-bottom: 4px solid #2b6f73;
  }

  .project-header h1 {
    color: #13294b;
    font-size: clamp(2rem, 4vw, 3.1rem);
    line-height: 1.12;
    margin: 0 0 0.8rem;
  }

  .project-header p {
    color: #334155;
    font-size: 1.08rem;
    max-width: 780px;
    margin: 0;
  }

  .kicker {
    color: #8a3b2f;
    font-size: 0.85rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    margin-bottom: 0.55rem;
    text-transform: uppercase;
  }

  .section {
    padding: 2rem 0;
    border-bottom: 1px solid #d8d2c3;
  }

  .section h2 {
    color: #13294b;
    font-size: 1.5rem;
    line-height: 1.25;
    margin: 0 0 0.8rem;
  }

  .section p {
    max-width: 860px;
  }

  .idea-list {
    padding-left: 1.35rem;
    max-width: 900px;
  }

  .idea-list li {
    margin-bottom: 0.9rem;
  }

  .field-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1rem;
  }

  .field-list code {
    background: #e7eee8;
    border: 1px solid #c8d8ce;
    border-radius: 6px;
    color: #23443d;
    padding: 0.2rem 0.45rem;
  }

  .chart-grid {
    display: grid;
    gap: 1.4rem;
    margin-top: 1.2rem;
  }

  .chart-panel {
    background: #ffffff;
    border: 1px solid #d8d2c3;
    border-radius: 8px;
    padding: 1rem;
  }

  .chart-panel h3 {
    color: #13294b;
    font-size: 1.1rem;
    margin: 0 0 0.8rem;
  }

  .chart-panel img {
    display: block;
    width: 100%;
    height: auto;
    border: 1px solid #e5e1d8;
    border-radius: 6px;
  }

  .caption {
    color: #52606d;
    font-size: 0.95rem;
    margin: 0.8rem 0 0;
  }

  .recommendation {
    background: #e7eee8;
    border-left: 5px solid #2b6f73;
    border-radius: 8px;
    padding: 1rem 1.15rem;
    margin-top: 1rem;
  }

  code {
    background: #ece7dc;
    border-radius: 5px;
    padding: 0.1rem 0.28rem;
  }
</style>

<div class="page-wrap">

  <header class="project-header">
    <div class="kicker">COMP110 EX09</div>
    <h1>Data Analysis for Course Improvement</h1>
    <p>This project uses anonymized COMP110 survey data to evaluate whether optional pre-lecture videos would create value for students by helping them prepare before live class meetings.</p>
  </header>

  <section class="section">
    <h2>Project Focus</h2>
    <p>The improvement idea I chose to analyze is a pilot set of optional pre-lecture videos for topics that students commonly find difficult. The stakeholder group most directly served is students enrolled in COMP110, because the videos would give them a low-pressure way to preview unfamiliar concepts before lecture.</p>
    <p>The analysis looks for evidence that students want this resource, especially students who report higher course difficulty or lower self-reported understanding.</p>
    <div class="field-list" aria-label="Survey fields used in the analysis">
      <code>pre_lecture_videos</code>
      <code>difficulty</code>
      <code>understanding</code>
      <code>prior_exp</code>
      <code>ls_effective</code>
      <code>unc_status</code>
    </div>
  </section>

  <section class="section">
    <h2>Brainstormed Improvement Ideas</h2>
    <ol class="idea-list">
      <li><strong>Optional pre-lecture videos for difficult topics.</strong> This creates value for students by letting them preview new concepts at their own pace before class.</li>
      <li><strong>More examples connected to non-CS fields.</strong> This creates value for students outside the CS major and for the societal workforce by making programming feel more relevant across disciplines.</li>
      <li><strong>Expanded office-hour capacity before major deadlines.</strong> This creates value for students by reducing help-seeking bottlenecks and for instructional staff by distributing support more intentionally.</li>
      <li><strong>Structured peer study-group matching.</strong> This creates value for students by adding another layer of academic support outside formal office hours.</li>
      <li><strong>A mid-semester pacing and difficulty checkpoint.</strong> This creates value for instructional staff and the academic institution by giving the course team earlier feedback for targeted adjustments.</li>
    </ol>
  </section>

  <section class="section">
    <h2>Idea With Missing Data</h2>
    <p>The idea least supported by the current survey is structured peer study-group matching. The survey does not directly ask whether students already study with peers, whether they want help finding study partners, or whether they would opt in to a matching system.</p>
    <p>A future survey could collect this data by asking how often students currently work with classmates, whether they would use an opt-in matching tool, what format they prefer for study groups, and whether peer study improves their confidence or assignment progress.</p>
  </section>

  <section class="section">
    <h2>Chosen Analysis</h2>
    <p>I chose to analyze optional pre-lecture videos because the survey contains a direct measure of student interest in that exact resource. The idea also has practical value: once a short video is produced, it can be reused by many students and future course sections.</p>
    <p>For the notebook analysis, I loaded the survey with <code>read_csv_rows</code>, inspected it with <code>head</code>, reorganized it with <code>columnar</code>, selected the relevant fields with <code>select</code>, summarized response frequencies with <code>count</code>, and used a helper function to convert valid Likert-scale strings into numeric values for plotting.</p>
  </section>

  <section class="section">
    <h2>Analysis Summary</h2>
    <p>The first chart summarizes overall interest in optional pre-lecture videos. The distribution leans toward agreement, with the highest response levels appearing more often than the lowest response levels. That suggests the idea has broad student demand.</p>
    <p>The second and third charts compare interest in pre-lecture videos against students' reported difficulty and understanding. These relationships are not perfectly linear, but they show that interest remains high among students who report struggling with the course. That makes the feature especially relevant as an optional support resource rather than a required replacement for lecture.</p>
  </section>

  <section class="section">
    <h2>Visualizations</h2>
    <div class="chart-grid">
      <article class="chart-panel">
        <h3>Overall Interest in Pre-Lecture Videos</h3>
        <img src="{{ '/static/imgs/pre_lecture_video_interest.png' | relative_url }}" alt="Count plot showing student ratings for interest in optional pre-lecture videos">
        <p class="caption">This count plot shows how many students selected each rating for the <code>pre_lecture_videos</code> survey item. Ratings near 7 indicate stronger agreement that the videos would be helpful.</p>
      </article>

      <article class="chart-panel">
        <h3>Interest Compared With Course Difficulty</h3>
        <img src="{{ '/static/imgs/difficulty_vs_prelecture.png' | relative_url }}" alt="Scatterplot comparing perceived course difficulty with interest in pre-lecture videos">
        <p class="caption">This scatterplot compares perceived course difficulty with interest in pre-lecture videos. It helps evaluate whether students who find the course more difficult also tend to support the extra preparation resource.</p>
      </article>

      <article class="chart-panel">
        <h3>Interest Grouped by Self-Reported Understanding</h3>
        <img src="{{ '/static/imgs/understanding_vs_prelecture.png' | relative_url }}" alt="Box plot comparing self-reported understanding groups with interest in pre-lecture videos">
        <p class="caption">This box plot groups pre-lecture-video interest by self-reported understanding. It shows whether students who feel less confident with the material still report strong demand for pre-lecture support.</p>
      </article>
    </div>
  </section>

  <section class="section">
    <h2>Conclusion</h2>
    <p>The survey data supports piloting optional pre-lecture videos, but it does not prove that the videos would directly improve grades or understanding. The strongest evidence is that student interest is generally high and remains high for students who report higher difficulty or lower confidence.</p>
    <p>The main trade-offs are production time, maintenance work when course content changes, and the possibility that optional videos may be underused by students who would benefit from them. A full-course rollout would require more staff time than the survey alone can justify.</p>
    <div class="recommendation">
      <p><strong>Recommendation:</strong> COMP110 should pilot short optional pre-lecture videos for a small set of difficult topics, then collect follow-up data on video usage, preparation, confidence, and assignment outcomes before expanding the idea.</p>
    </div>
  </section>

</div>

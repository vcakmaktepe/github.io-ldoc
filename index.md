---
layout: default
---

<style>
  body {
    background: #f6f8fb;
    color: #172033;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
    line-height: 1.65;
  }

  .page-wrap {
    max-width: 980px;
    margin: 0 auto;
    padding: 2rem 1.25rem 4rem;
  }

  .hero {
    background: linear-gradient(135deg, #13294b, #4b9cd3);
    color: white;
    border-radius: 20px;
    padding: 2.5rem;
    margin-bottom: 2rem;
    box-shadow: 0 18px 40px rgba(19, 41, 75, 0.22);
  }

  .hero h1 {
    margin-top: 0;
    margin-bottom: 0.75rem;
    font-size: 2.4rem;
    line-height: 1.15;
  }

  .hero p {
    margin-bottom: 0;
    font-size: 1.08rem;
    max-width: 780px;
  }

  .card {
    background: white;
    border-radius: 18px;
    padding: 1.6rem 1.8rem;
    margin: 1.4rem 0;
    box-shadow: 0 10px 28px rgba(15, 23, 42, 0.08);
    border: 1px solid #e6edf5;
  }

  .card h2 {
    margin-top: 0;
    color: #13294b;
    border-bottom: 2px solid #e7f1fb;
    padding-bottom: 0.45rem;
  }

  .pill-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
    margin-top: 1rem;
  }

  .pill {
    background: #e7f1fb;
    color: #13294b;
    border-radius: 999px;
    padding: 0.35rem 0.8rem;
    font-size: 0.92rem;
    font-weight: 600;
  }

  .idea-list li {
    margin-bottom: 0.9rem;
  }

  .figure-card {
    background: #ffffff;
    border: 1px solid #dbe7f3;
    border-radius: 18px;
    padding: 1rem;
    margin: 1.5rem 0;
    box-shadow: 0 8px 24px rgba(15, 23, 42, 0.07);
  }

  .figure-card img {
    width: 100%;
    max-width: 900px;
    display: block;
    margin: 0 auto;
    border-radius: 12px;
    border: 1px solid #edf2f7;
  }

  .caption {
    color: #526176;
    font-size: 0.95rem;
    margin-top: 0.8rem;
  }

  .recommendation {
    background: #eef7ff;
    border-left: 6px solid #4b9cd3;
  }

  code {
    background: #f0f4f8;
    border-radius: 5px;
    padding: 0.1rem 0.28rem;
  }
</style>

<div class="page-wrap">

<section class="hero">
  <h1>COMP110 EX09: Data Analysis for Continuous Improvement</h1>
  <p>This project analyzes whether optional pre-lecture videos could improve the COMP110 learning experience by helping students prepare before live lecture.</p>
</section>

<section class="card">
  <h2>Project Focus</h2>
  <p>This project analyzes whether COMP110 should add optional pre-lecture videos to help students prepare before class. The central idea is that preview videos could create value for students who need more time to process new programming concepts before encountering them in live lecture.</p>

  <p>The analysis uses anonymized COMP110 survey data from both course sections.</p>

  <div class="pill-row">
    <span class="pill">pre_lecture_videos</span>
    <span class="pill">difficulty</span>
    <span class="pill">understanding</span>
    <span class="pill">prior_exp</span>
    <span class="pill">ls_effective</span>
  </div>
</section>

<section class="card">
  <h2>Brainstormed Course Improvement Ideas</h2>
  <ol class="idea-list">
    <li>The course should offer optional pre-lecture video content covering each lecture topic because it would allow students who need more preparation time to preview material at their own pace before class.</li>
    <li>The course should integrate more domain-specific examples, such as biology, economics, psychology, and public health examples, into programming exercises because this would make the material feel more relevant to students outside the computer science major.</li>
    <li>The course should expand the number of available office hours appointments during the 48-hour window before major assignments are due because this would reduce help-seeking bottlenecks.</li>
    <li>The course should introduce a structured peer-tutoring or study-group matching system because it would give students another layer of support outside formal office hours.</li>
    <li>The course should include a mid-semester difficulty and pacing checkpoint because this would give instructional staff real-time feedback and allow them to adjust course support before the end of the semester.</li>
  </ol>
</section>

<section class="card">
  <h2>Idea With Missing Data</h2>
  <p>The idea least supported by the current survey data is the structured peer-tutoring or study-group matching system. The survey does not directly ask whether students currently study with peers, whether they want peer-matching support, or whether they would participate in a structured study group.</p>
  <p>To collect better data in the future, the course could add survey questions asking students how often they study with peers, whether they would use a formal study-group matching system, and whether peer collaboration improves their confidence.</p>
</section>

<section class="card">
  <h2>Chosen Analysis</h2>
  <p>The idea selected for analysis is optional pre-lecture videos. This idea was chosen because the dataset directly includes the <code>pre_lecture_videos</code> column, which measures student interest in this feature on a 1-7 agreement scale.</p>
  <p>This idea is valuable because pre-lecture videos are scalable. Once created, they can be reused across sections and semesters. Compared with expanding office hours, which requires ongoing staff time, pre-lecture videos have a larger potential reach with a lower recurring cost.</p>
</section>

<section class="card">
  <h2>Analysis Summary</h2>
  <p>The analysis combined the <code>survey_izzi.csv</code> and <code>survey_alyssa.csv</code> datasets into one larger table. After combining the datasets, I selected the columns most relevant to the research question: <code>prior_exp</code>, <code>difficulty</code>, <code>understanding</code>, <code>pre_lecture_videos</code>, <code>ls_effective</code>, and <code>unc_status</code>.</p>
  <p>Overall, the data suggests meaningful support for optional pre-lecture videos. Students who reported higher difficulty or lower understanding tended to show stronger interest in having pre-lecture videos available.</p>
</section>

<section class="card">
  <h2>Visualization 1: Overall Interest in Pre-Lecture Videos</h2>
  <div class="figure-card">
    <img src="{{ site.baseurl }}/static/imgs/pre_lecture_video_interest.png" alt="Count plot showing student interest in optional pre-lecture videos">
    <p class="caption">This count plot shows the distribution of student responses to the <code>pre_lecture_videos</code> question. A concentration of responses near 5, 6, and 7 would indicate broad support for the feature.</p>
  </div>
</section>

<section class="card">
  <h2>Visualization 2: Pre-Lecture Video Interest vs. Course Difficulty</h2>
  <div class="figure-card">
    <img src="{{ site.baseurl }}/static/imgs/difficulty_vs_prelecture.png" alt="Scatterplot comparing course difficulty and interest in pre-lecture videos">
    <p class="caption">This scatterplot compares students' perceived course difficulty with their interest in optional pre-lecture videos. The goal is to see whether students who find the course more difficult are also more likely to support this resource.</p>
  </div>
</section>

<section class="card">
  <h2>Visualization 3: Pre-Lecture Video Interest by Understanding Level</h2>
  <div class="figure-card">
    <img src="{{ site.baseurl }}/static/imgs/understanding_vs_prelecture.png" alt="Box plot comparing understanding level and interest in pre-lecture videos">
    <p class="caption">This box plot compares pre-lecture-video interest across different levels of self-reported understanding. Lower understanding values represent students who feel more lost, while higher values represent students who feel more confident with the material.</p>
  </div>
</section>

<section class="card">
  <h2>Conclusion</h2>
  <p>The analysis provides support for implementing optional pre-lecture videos in COMP110. The strongest reason is that the feature appears to align with student need: students who experience higher difficulty or lower understanding tend to express stronger interest in having pre-lecture content available.</p>
  <p>This does not prove that pre-lecture videos would directly improve performance, because the survey data is observational rather than experimental. However, the relationship between student difficulty, understanding, and interest in pre-lecture videos suggests that the idea is worth piloting.</p>
  <p>The main trade-off is production cost. High-quality pre-lecture videos require instructor time to plan, record, edit, and maintain. There is also a risk that optional videos may be underused by students who would benefit from them most.</p>
</section>

<section class="card recommendation">
  <h2>Recommendation</h2>
  <p>COMP110 should pilot optional pre-lecture videos for selected difficult topics rather than immediately producing videos for the entire course. A limited pilot would allow instructional staff to test whether the videos actually improve student preparation and understanding before committing to a larger implementation.</p>
</section>

</div>
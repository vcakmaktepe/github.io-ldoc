---
layout: default
---

# COMP110 EX09: Data Analysis for Continuous Improvement

## Project Focus

This project analyzes whether COMP110 should add optional pre-lecture videos to help students prepare before class. The central idea is that preview videos could create value for students who need more time to process new programming concepts before encountering them in live lecture.

The analysis uses anonymized COMP110 survey data from both course sections. The main variables examined are:

- `pre_lecture_videos`: student support for optional pre-lecture videos
- `difficulty`: how difficult students find COMP110
- `understanding`: how well students feel they understand the material
- `prior_exp`: students' prior programming experience
- `ls_effective`: perceived effectiveness of lesson videos

## Brainstormed Course Improvement Ideas

1. The course should offer optional pre-lecture video content covering each lecture topic because it would allow students who need more preparation time to preview material at their own pace before class. This creates value for students with less prior programming experience who may feel overwhelmed by the pace of live lecture.

2. The course should integrate more domain-specific examples, such as biology, economics, psychology, and public health examples, into programming exercises because this would make the material feel more relevant to students outside the computer science major.

3. The course should expand the number of available office hours appointments during the 48-hour window before major assignments are due because this would reduce help-seeking bottlenecks and benefit students who rely on one-on-one instructional support.

4. The course should introduce a structured peer-tutoring or study-group matching system because it would give students another layer of support outside formal office hours.

5. The course should include a mid-semester difficulty and pacing checkpoint because this would give instructional staff real-time feedback and allow them to adjust course support before the end of the semester.

## Idea With Missing Data

The idea least supported by the current survey data is the structured peer-tutoring or study-group matching system. The survey does not directly ask whether students currently study with peers, whether they want peer-matching support, or whether they would participate in a structured study group.

To collect better data in the future, the course could add survey questions asking students how often they study with peers, whether they would use a formal study-group matching system, and whether peer collaboration improves their confidence. These responses could then be analyzed alongside existing variables such as `difficulty`, `understanding`, and `oh_visits`.

## Chosen Analysis

The idea selected for analysis is optional pre-lecture videos. This idea was chosen because the dataset directly includes the `pre_lecture_videos` column, which measures student interest in this feature on a 1-7 agreement scale.

This idea is valuable because pre-lecture videos are scalable. Once created, they can be reused across sections and semesters. Compared with expanding office hours, which requires ongoing staff time, pre-lecture videos have a larger potential reach with a lower recurring cost. The feature could especially help students who report high difficulty or low understanding.

## Analysis Summary

The analysis combined the `survey_izzi.csv` and `survey_alyssa.csv` datasets into one larger table. After combining the datasets, I selected the columns most relevant to the research question: `prior_exp`, `difficulty`, `understanding`, `pre_lecture_videos`, `ls_effective`, and `unc_status`.

The first step was to count the distribution of responses to `pre_lecture_videos`. This showed whether students generally agreed or disagreed that optional pre-lecture videos would be helpful. The analysis then compared interest in pre-lecture videos with perceived course difficulty and self-reported understanding.

Overall, the data suggests meaningful support for optional pre-lecture videos. Students who reported higher difficulty or lower understanding tended to show stronger interest in having pre-lecture videos available. This supports the idea that preview material could help students who need additional preparation before live instruction.

## Visualization 1: Overall Interest in Pre-Lecture Videos

![Overall Interest in Optional Pre-Lecture Videos]({{ site.baseurl }}/static/imgs/pre_lecture_video_interest.png)

This visualization shows the distribution of student responses to the `pre_lecture_videos` question. The purpose of this chart is to determine whether support for pre-lecture videos exists across the course population as a whole.

If most responses cluster toward 5, 6, or 7, that indicates students generally agree that optional pre-lecture videos would be useful.

## Visualization 2: Pre-Lecture Video Interest vs. Course Difficulty

![Pre-Lecture Video Interest vs. Course Difficulty]({{ site.baseurl }}/static/imgs/difficulty_vs_prelecture.png)

This scatterplot compares students' perceived course difficulty with their interest in optional pre-lecture videos. The main question is whether students who find COMP110 more difficult are also more likely to support pre-lecture videos.

A concentration of higher pre-lecture-video ratings among students with higher difficulty ratings would suggest that the proposed feature targets a real area of student need.

## Visualization 3: Pre-Lecture Video Interest by Understanding Level

![Pre-Lecture Video Interest Grouped by Understanding]({{ site.baseurl }}/static/imgs/understanding_vs_prelecture.png)

This box plot compares pre-lecture-video interest across different levels of self-reported understanding. Since `understanding` is rated from 1 to 7, lower values represent students who feel more lost, while higher values represent students who feel they understand the material more fully.

If students with lower understanding ratings show higher median interest in pre-lecture videos, that would support the idea that these videos could help students who are struggling most.

## Conclusion

The analysis provides support for implementing optional pre-lecture videos in COMP110. The strongest reason is that the feature appears to align with student need: students who experience higher difficulty or lower understanding tend to express stronger interest in having pre-lecture content available.

This does not prove that pre-lecture videos would directly improve performance, because the survey data is observational rather than experimental. However, the relationship between student difficulty, understanding, and interest in pre-lecture videos suggests that the idea is worth piloting.

The main trade-off is production cost. High-quality pre-lecture videos require instructor time to plan, record, edit, and maintain. There is also a risk that optional videos may be underused by students who would benefit from them most. For this reason, the videos should be short, clearly connected to upcoming lectures, and organized by topic.

A useful future extension would be a controlled comparison between sections or units that use pre-lecture videos and those that do not. The course could also track whether students who watch pre-lecture videos report higher understanding, lower difficulty, or reduced need for office hours support.

## Recommendation

COMP110 should pilot optional pre-lecture videos for selected difficult topics rather than immediately producing videos for the entire course. A limited pilot would allow instructional staff to test whether the videos actually improve student preparation and understanding before committing to a larger implementation.

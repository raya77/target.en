---
keywords: AB;A/B;AB...n;mistakes;pitfalls;mistake;pitfall;significance;winner;statistically difference;statistical;statistical power;traffic allocation;allocation;
description: Learn how to avoid the most common pitfalls and mistakes that companies make when performing A/B testing in Adobe [!DNL Target] and other testing solutions.
title: How Do I Avoid Common A/B Testing Mistakes?
feature: A/B Tests
exl-id: db085819-1a85-4936-bdc9-7501cf9b26ce
---
# Ten common A/B testing pitfalls and how to avoid them

A/B testing in [!DNL Adobe Target] forms the backbone of most digital marketing optimization programs, helping marketers offer optimized and targeted experiences to their visitors and customers. This section outlines ten of the most significant pitfalls that companies fall prey to when performing A/B testing. It also includes ways to avoid them, so your company can achieve greater ROI through its testing efforts and have greater confidence in its reported A/B test results.

## Pitfall 1: Ignoring the effects of the significance level {#section_55F5577A13C6470BA1417C2B735C6B1D}

How likely is it that your test reports a significant difference in conversion rate between two offers when in fact there is none? That's what the *significance level* of a test helps determine. Such misleading findings are often called a false positive, and in the world of statistics, are called a Type I error (if you incorrectly reject the null hypothesis that is actually true).

When you specify the significance level of an A/B test, you're making a trade-off between your tolerance for accepting that one experience is better than the other when it really isn't (Type I error or "false positive") versus seeing no statistical difference between the experiences when there actually is a true difference (Type II error or "false negative"). The *confidence level* is determined before a test is run.

The *confidence interval*, which is determined after a test is complete, is impacted by three key factors: sample size of the test, significance level, and population standard deviation. Because the marketer selected the significance level before the test is designed and the population standard deviation can't be impacted, the only "controllable" factor is the sample size. The sample size required for a confidence interval you are comfortable with, and the resulting time it takes to reach that sample size, is a key decision a marketer must determine during the test design.

Another directly related term, the *confidence level*, takes more of a glass half-full approach. Rather than stating the likelihood that you'll get a false positive, as the significance level does, the confidence level represents the likelihood that your test will not make that mistake.

Confidence level and significance level are directly related because:

100% - confidence level = significance level

In A/B testing, marketers often use 95% confidence levels. Clearly, based on the above equation, that corresponds to a significance level of 5%. Testing with a 95% confidence level means you have a 5% chance of detecting a statistically significant lift, even when in reality, there's no difference between the offers.

As the graph below illustrates, the more tests that you run, the more likely at least one of those tests will result in a false positive. For example, if you run 10 tests using a 95% confidence level, there is approximately a 40% chance that you will detect one or more false positives (given that there is no real lift: Pr(at least one false positive) = 1 - Pr(no false positives) = 1 - 0.95^10 = 40%).

![](assets/pitfalls1.png)

In a marketing organization, 95% usually constitutes a reasonable trade-off between the risk of a false positive and false negatives.

However, two situations warrant paying close attention to the significance level and its implications for test results: post-test segmentation and testing multiple offers.

* **Post-Test Segmentation:** Marketers often slice and dice the results of a test based on visitor segments after the A/B test concludes. Common segments include browser type, device type, geographic areas, time of day, and new versus returning visitors. This practice, known as post-test segmentation, provides excellent insight into visitor segments. In turn, marketers can use these insights to create better-targeted and more-relevant and differentiated content.

  If there is no real difference in conversion rate, each time you test a segment, the probability of a false positive equals the significance level. And, as mentioned, the more tests you run, the greater the likelihood that you'll experience at least one false positive among those tests. In essence, each post-test segment represents a separate test. With a significance level of 5%, on average you'll fall prey to one false positive every time you look at 20 post-test segments. The chart above shows how that likelihood increases.

  As mentioned above, the more tests you run, the greater the likelihood that you'll experience at least one false positive among those tests. In essence, each post-test segment represents a separate test, which increases the likelihood of a false positive. This increase can be even more significant if segments are correlated.

  Should you simply not do post-test segmentation? No, post-test segments are valuable. Instead, to avoid this cumulative false positive issue with post-test segmentation, after you've identified a post-test segment, consider testing it in a new test. Alternatively, you can apply the Bonferroni correction, discussed next. 

* **Testing Multiple Offers:** Marketers frequently test more than two offers (or experiences) against each other. That's why you sometimes see A/B testing solutions called A/B/n testing, where n is the number of offers that you are testing simultaneously.

  It's important to note that *each* offer tested has a false positive rate equal to the significance level, as described above. Again, you are effectively running multiple tests when several offers are pitted against each other within a single test environment. For example, if you compare five offers in an A/B/C/D/E test, effectively you form four comparisons: control to B, control to C, control to D, control to E. With a confidence level of 95%, rather than the 5% probability of a false positive, you actually have 18.5%. 2

  To keep your overall confidence level at 95% and avoid this issue, you apply what is known as the Bonferroni correction. Using this correction, you simply divide the significance level by the number of comparisons to come up with the significance level that you need to achieve a 95% confidence level.

  Applying the Bonferroni correction to the example above, you would use a 5%/4 = 1.25% significance level, which is the same as a 98.75% confidence level for an individual test (100% - 1.25% = 98.75%). This adjustment maintains the effective confidence level at 95% when you have four tests, as in the described example.

## Pitfall 2: Declaring winners of multiple offer tests with no statistically significant difference {#section_FA83977C71DB4F69B3D438AF850EF3B6}

With multiple offer testing, marketers often declare the offer with the highest lift as the test winner, even though there is no statistically significant difference between the winner and the runner-up. This situation occurs when the difference between the alternatives is smaller than the difference between the alternatives and the control. The figure below illustrates this concept, with the black error bars representing 95% lift confidence intervals. The true lift for each offer relative to the control offer is 95% likely to be included within the confidence interval-the range shown by the error bars.

![](assets/pitfalls2.png)

Offers A and B have the highest observed lift during the test, and it would be unlikely that offer C would outperform those offers in a future test, because the confidence interval of C does not even overlap with the confidence intervals of A or B. However, even though offer A has the highest observed lift during the test, it is quite possible that offer B could perform better in a future test because the confidence intervals overlap.

The takeaway here is that both offers A and B should be considered winners of the test.

It's typically not feasible to run the test long enough to identify the true relative performance of the alternatives, and oftentimes the difference in performance between the alternatives is too small to substantially impact the conversion rate. In such cases, you can interpret the outcome as a tie and use other considerations, such as strategy or alignment with other elements of the page, to determine which offer to implement. With multiple tests, you must be open to more than one winner, which in some cases considerably opens up the possibilities for the direction to take with your website development.

Note that if you do want to identify the offer with the highest conversion rate, you are comparing all offers to every other offer. In the example above, you have n = 5 offers—you have to make n(n-1)/2 comparisons, or 5&#42;(5-1)/2 = 10 comparisons. In this case, the Bonferroni correction requires that the significance level of the test be 5%/10 = 0.5%, which corresponds to a confidence level of 99.5%. However, such a high confidence level might require you to run the test for an unreasonably long period of time.

## Pitfall 3: Ignoring the effects of statistical power {#section_0D517079B7D547CCAA75F80981CBE12A}

Statistical power is the probability that a test will detect a real difference in conversion rate between offers. Because of the random, or as statisticians like to call it, "stochastic," nature of conversion events, a test might not show a statistically significant difference, even when a real difference exists in conversion rate between two offers in the long run. Call it bad luck or by chance. Failing to detect a true difference in conversion rate is called a false negative or a Type II error.

There are two key factors that determine the power of a test. First is the sample size, that is, the number of visitors included in the test. Second is the magnitude of the difference in conversion rate you want the test to detect. Perhaps this is somewhat intuitive, but if you are interested in only detecting large conversion rate differences, there's a much higher probability that the test will actually detect such large differences—kind of like discovering that you have an elephant in your living room versus a fly while looking through a paper towel tube. Along those lines, the smaller the difference you want to detect, the larger the sample size, and therefore, time to get that larger sample size, you require.

Today's marketers under-power a remarkable number of tests. In other words, they use a sample size that is too small. That means that they have a slim chance of detecting true positives, even when a substantial difference in conversion rate actually exists. In fact, if you continually run underpowered tests, the number of false positives can be comparable to, or even dominate, the number of true positives. This often leads to implementing neutral changes to a site (a waste of time) or changes that actually reduce conversion rates.

![](assets/pitfalls3.png)

To avoid under-powering your test, consider that a typical standard for a well-powered test includes a confidence level of 95% and a statistical power of 80%. Such a test offers a 95% probability that you'll avoid a false positive and an 80% probability that you'll avoid a false negative.

## Step 4: Using one-tailed tests {#section_8BB136D1DD6341FA9772F4C31E9AA37C}

One-tailed tests require a smaller observed difference in conversion rates between the offers to call a winner at a certain significance level. This seems appealing because winners can be called earlier and more often than when using two-tailed tests. But in keeping with the saying, "There's no free lunch," one-tailed tests come at an expense.

In a one-tailed test, you test whether offer B is better than offer A. The direction of the test has to be determined before the test commences, or "a priori" in statistics-speak. In other words, you must decide whether to test for B being better than A or A being better than B *before* initiating the test. However, if you look at the results of the A/B test and see that B is doing better than A and *then* decide to do a one-tailed test to see whether that difference is statistically significant, you are violating the assumptions behind the statistical test. Violating the assumptions of the test means that your confidence intervals are unreliable and the test has a higher false positive rate than you would expect.

You might view a one-tailed test as putting an offer on trial with a judge who has already made up his or her mind. In a one-tailed test, you've already decided what the winning offer will be and are out to prove it, rather than giving each experience an equal chance to prove itself as the winner. One-tailed tests should only be used in the rare situations in which you are only interested in whether one offer is better than the other and not the other way around. To avoid the issue of the one-tailed test, use an A/B testing solution that always uses two-tailed tests, such as [!DNL Adobe Target].

## Pitfall 5: Monitoring tests {#section_EA42F8D5967B439284D863C46706A1BA}

Marketers frequently monitor A/B tests until the test determines a significant result. After all, why test after you've achieved statistical significance?

Unfortunately, it's not that simple. Not to throw a wrench in the works, but it turns out that monitoring the results adversely impacts the effective statistical significance of the test. It actually greatly increases the likelihood of false positives and makes your confidence intervals untrustworthy.

This might seem confusing. It sounds like we are saying that just from looking at your results mid-test, you can cause them to lose their statistical significance. That's not exactly what's going on. The following example explains why.

Let's say you simulate 10,000 conversion events of two offers, with both offers having 10% conversion rates. Because the conversion rates are the same, you should detect no difference in conversion lift when you test the two offers against each other. Using a 95% confidence interval, the test results in the expected 5% false positive rate when it is evaluated after collecting all 10,000 observations. So if we run 100 of these tests, on average we will get five false positives (in actuality, all positives are false in this example because there is no difference in conversion rate between the two offers). However, if we evaluate the test 10 times during the test—every 1,000 observations—it turns out that the false positive rate jumps up to 16%. Monitoring the test has more than tripled the risk of false positives! How can this be?

To understand why this occurs, you have to consider the different actions taken when a significant result is detected and when it is not detected. When a statistically significant result is detected, the test is stopped and a winner is declared. However, if the result is not statistically significant, we allow the test to continue. This situation strongly favors the positive outcome, and hence, distorts the effective significance level of the test.

To avoid this problem, you should determine an adequate length of time the test will run before initiating the test. While it's fine to look at the test results during the test to make sure that you implemented the test correctly, do not draw conclusions or stop the test before the required number of visitors is reached. In other words, no peeking!

## Pitfall 6: Stopping tests prematurely {#section_DF01A97275E44CA5859D825E0DE2F49F}

It is tempting to stop a test if one of the offers performs much better or worse than the others in the first few days of the test. However, when the number of observations is low, there is a high likelihood that a positive or negative lift will be observed just by chance because the conversion rate is averaged over a low number of visitors. As the test collects more data points, the conversion rates converge toward their true long-term values.

The figure below shows five offers that have the same long-term conversion rate. Offer B had a poor conversion rate for the first 2,000 visitors, and it takes a long time before the estimated conversion rate returns to the true long-term rate.

![](assets/pitfalls4.png)

This phenomenon is known as "regression to the mean," and can lead to disappointment when an offer that performed well during the initial days of a test fails to keep up this level of performance in the long run. It can also lead to lost revenue when a good offer is not implemented because it happened to underperform in the early days of a test just by chance.

Much like the pitfall of monitoring your test, the best way to avoid these issues is to determine an adequate number of visitors before running the test and then let the test run until this number of visitors has been exposed to the offers.

## Pitfall 7: Changing the traffic allocation during the testing period {#allocation}

We recommend that you do not change the traffic allocation percentages during the testing period because this can skew your test results until the data normalizes.
For example, suppose you have an A/B Test activity in which 80% of the traffic is assigned to Experience A (the control) and 20% of the traffic is assigned to Experience B. During the testing period, you change the allocation to 50% for each experience. A few days later, you change the traffic allocation to 100% to Experience B.

In this scenario, how are users assigned to experiences?

If you manually change the allocation split to 100% for Experience B, visitors who were originally allocated to Experience A (the control) remain in their initially assigned experience (Experience A). The change in traffic allocation impacts new entrants only.

If you want to change percentages or greatly affect the flow of visitors into each experience, we recommend that you create a new activity or copy the activity and then edit the traffic allocation percentages.

If you change the percentages for different experiences during the testing period, it takes a few days for the data to normalize, especially if many purchasers are returning visitors. 
As another example, if your A/B Test’s traffic allocation is split 50/50, and then you change the split to 80/20, for the first few days after that change the results might look skewed. If the average time to conversion is high, meaning it takes someone several hours or even days to make a purchase, these delayed conversions can affect your reports. So, in that first experience where the number went from 50% to 80%, and the average time to conversion is two days, only visitors from 50% of the population are converting on the first day of the test, although today 80% of the population is entering into the experience. This makes it look like the conversion rate plummeted, but it will normalize again after these 80% of visitors have taken two days to convert.

## Pitfall 8: Not considering novelty effects {#section_90F0D24C40294A8F801B1A6D6DEF9003}

Other unexpected things can happen if we don't allow enough time for running a test. This time the problem is not a statistics problem; it's simply a reaction to change by the visitors. If you change a well-established part of your website, returning visitors might at first engage less fully with the new offer because of changes to their usual workflow. This can temporarily cause a superior new offer to perform less optimally until returning visitors become accustomed to it—a small price to pay given the long-term gains that the superior offer will deliver.

To determine if the new offer underperforms because of a novelty effect or because it's truly inferior, you can segment your visitors into new and returning visitors and compare the conversion rates. If it's just the novelty effect, the new offer will win with new visitors. Eventually, as returning visitors get accustomed to the new changes, the offer will win with them, too.

The novelty effect can also work in reverse. Visitors often react positively to a change just because it introduces something new. After a while, as the new content becomes stale or less exciting to the visitor, the conversion rate drops. This effect is harder to identify, but carefully monitoring changes in the conversion rate is key to detecting this.

## Pitfall 9: Not considering differences in the consideration period {#section_B166731B5BEE4E578816E351ECDEA992}

The consideration period is the time period from when the A/B testing solution presents an offer to a visitor to when the visitor converts. This can be important with offers that affect the consideration period substantially—for example, an offer that implies a deadline, such as "Time-limited offer—Purchase by this Sunday."

Such offers nudge visitors to convert sooner and will be favored if the test is stopped immediately after the offer expires, because the alternative offer might have a longer deadline or no deadline, and therefore, a longer consideration period. The alternative would get conversions in the period after the termination of the test, but if you stop the test at the end of the deadline, further conversions do not get counted toward the test conversion rate.

The figure below shows two offers that two different visitors see at the same time on a Sunday afternoon. The consideration period for offer A is short, and the visitor converts later that day. However, offer B has a longer consideration period, and the visitor who saw offer B thinks about the offer for a while and ends up converting Monday morning. If you stop the test Sunday night, the conversion associated with offer A is counted toward offer A's conversion metric, whereas the conversion associated with offer B is not counted toward offer B's conversion metric. This puts offer B at a significant disadvantage.

![](assets/pitfalls5.png)

To avoid this pitfall, allow some time for visitors who were exposed to the test offers to convert after a new entry to the test has been stopped. This step gives you a fair comparison of the offers.

## Pitfall 10: Using metrics that do not reflect business objectives {#section_F0CD6DC7993B4A6F9BEEBB31CD1D9BEE}

Marketers might be tempted to use high-traffic and low-variance conversion metrics in the upper funnel, such as click-through rate (CTR), to reach an adequate number of test conversions faster. However, carefully consider whether CTR is an adequate proxy for the business goal that you want to attain. Offers with higher CTRs can easily lead to lower revenue. This can happen when offers attract visitors with a lower propensity to buy, or when the offer itself-for example, a discount offer-simply leads to lower revenue.

![](assets/pitfalls6.png)

Consider the skiing offer below. It generates a much higher CTR than the cycling offer, but because visitors spend much more money on average when they follow the cycling offer, the expected revenue of putting the cycling offer in front of a given visitor is higher. Therefore, an A/B test with CTR as the metric would pick an offer that does not maximize revenue-the fundamental business objective.

![](assets/pitfalls7.png)

To avoid this issue, monitor your business metrics carefully to identify the business impact of the offers, or better yet, use a metric that is closer to your business goal, if possible.

## Conclusion: Success with A/B testing by recognizing and stepping around the pitfalls {#section_54D33248163A481EBD4421A786FE2B15}

After learning about the common A/B testing pitfalls, we hope you can identify when and where you might have fallen prey to them. We also hope we've armed you with a better understanding of some of the statistics and probability concepts involved in A/B testing that often feel like the domain of people with math degrees.

The steps below help you avoid these pitfalls and focus on achieving better results from your A/B testing:

* Carefully consider the right metric for the test based on relevant business goals. 
* Decide on a confidence level before the test starts, and adhere to this threshold when evaluating the results after the test ends. 
* Calculate the sample size (number of visitors) before the test is started. 
* Wait for the calculated sample size to be reached before stopping the test. 
* Adjust the confidence level when doing post-test segmentation or evaluating more than one alternative—for example, by using the Bonferroni correction.

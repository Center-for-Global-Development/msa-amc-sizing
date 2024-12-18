---
layout: default
title: How Much to Offer? A Practical Guide to Sizing Innovation Incentives
---
<link rel="stylesheet" href="style.css">

<script type="text/javascript">
  MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$', '$$'], ['\\[', '\\]']]
    }
  };
</script>
<script type="text/javascript" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

<script>
    function toggleDetails(id) {
        const details = document.getElementById(id);
        if (details.style.display === "none" || details.style.display === "") {
            details.style.display = "block";
        } else {
            details.style.display = "none";
        }
    }
</script>

<nav class="sidebar">
        <ol class="nav-list">
            <li><a href="#introduction">Introduction</a></li>
            <li>
                <a href="#conceptual_framework">Conceptual Framework</a>
                <ol>
                    <li><a href="#model_setup">Model Setup</a></li>
                </ol>
            </li>
            <li>
                <a href="#understanding_costs">Understanding Innovation Costs and Risks</a>
                <ol>
                    <li><a href="#key_components">Key components</a></li>
                    <li><a href="#expected_costs">Calculating Firms' Expected Costs</a></li>
                    <li><a href="#sourcing_parameters">Sourcing Parameter Estimates</a></li>
                </ol>
            </li>
            <li><a href="#program_size">Determining the Overall Program Size</a>
                <ol> 
                    <li><a href="#number_of_attempts">Target Number of Attempts</a></li>
                    <li><a href="#other-considerations">Other Considerations</a>
                        <ol>
                            <li><a href="#pipeline">Within and Across Firm Attempts</a></li>
                            <li><a href="#correlation-section">Correlated Probabilities</a></li>
                        </ol>
                    </li>
                </ol>
            </li>
            <li><a href="#total_costs">Total Costs and Cost Effectiveness</a>
                <ol>
                <li><a href="#additional_costs">Additional Cost Considerations</a></li>
                <li><a href="#cost_effectiveness">Cost Effectiveness</a></li>
                </ol>
            </li>
        </ol>
</nav>

<div class="takeaways-box">
    <h3> KEY TAKEAWAYS</h3>
    <ol>
        <li><strong>Sizing innovation incentives is challenging but not guesswork.</strong> Careful economic analysis and a deep understanding of the target innovation developer market can allow funders to optimize the incentive size to suit their program goals.</li>
        <li><strong>The necessary size of the incentive to spur private investments depends on three core factors:</strong></li>
            <ol>
                <li><strong>The costs and risks that firms face during development</strong>, including R&D, testing, regulatory, and commercialization expenses, adjusted for the probability of failure at each stage</li>
                <li><strong>The competitive dynamics between firms</strong>, recognizing that more competitors increase the chances of at least one success but also raise the incentive size needed since firms must factor in the risk of splitting rewards</li>
                <li><strong>The time value of money</strong>, accounting for firms' hurdle rate of returns and the often lengthy development timelines for major innovations</li>
            </ol>
        <li><strong>Larger pull funds can attract more firms and increase the chances of success, but they also increase total program costs.</strong></li>
    </ol>
</div>

<h2 id="introduction">1. Introduction</h2>
<span class="tooltip-word">Pull funding<span class="tooltip-text">"Pull funding" is incentive-based funding that rewards firms after achieving specific results or delivering a successful product. Since funders do not pay upfront, pull mechanisms place risk of technoligical success on the innovators.</span></span>, which conditions payment on successfully delivering results, can mobilize private investment to develop and deliver socially valuable innovations. Through mechanisms such as prizes and <span class = "tooltip-word">advance market commitments<span class="tooltip-text">Advanced market commitments are agreements where governments or organizations commit to purchasing or subsidizing a product once it is successfully developed, guaranteeing a market for manufacturers.</span></span>,  pull funding provides financial incentives to innovators, helping to correct common market failures that undermine innovation incentives for products with large public benefits but insufficient private returns. By linking payment to successful output, pull mechanisms require the innovator to bear the costs and risks of developing the target technology.  
    
However, these mechanisms face a critical design challenge: determining the right size of the incentive. If set too low, firms won't participate; if too high, the program wastes resources. How can funders determine the appropriate amount of pull funding needed to motivate private investment?

In this guide, we present a systematic framework for sizing innovation incentives. We begin by examining the key components that drive necesary incentive size: development costs, probability of success, competition, and time value of money. We then show how to build these elements into a practical framework for calculating minimum effective incentive sizes to achieve target probabilities of successful innovation. Finally, we explore how program design choices – from payment timing to market structure – affect both costs and probability of success.

Our approach draws from our experience evaluating incentive programs across sectors. By breaking down this complex challenge into manageable steps, we aim to help program designers develop more effective and efficient innovation incentives.

    
<h2 id="conceptual_framework">2. Conceptual Framework</h2>

Pull mechanisms mimic market incentives by committing to provide sufficient returns to innovators of socially valuable goods. Roughly speaking, when firms evaluate whether to enter a market, they consider whether expected revenues exceed expected costs. To that end, firms will weigh the crucial questions of any innovation investment: what is the likelihood of technological success? How much will it cost to pursue innovation? What is the expected market size and timing of future revenue? How much competition do they expect to face?

The size and structure of the pull mechanism will dictate the answer to these questions and, hence, determine how many firms try their hand at attempting to innovate. Increasing the amount of effort firms put into innovation or increasing the expected number of firms that choose to participate in pull mechanisms increases the probability that at least one attempt yields success. To determine the appropriate reward size, the designer of the pull mechanism, therefore, needs to consider the tradeoff between increasing the probability that firms succeed at innovation and the cost of the endeavor.

<h3 id="model_setup">Model Setup</h3>
When designing an innovation incentive, we need a systematic way to think about what motivates firms to participate. Let's start with a simplified view: Imagine a pharmaceutical company considering whether to develop a new vaccine. They know development will require significant upfront investment in research, clinical trials, and manufacturing capacity. They also know there's a high chance of failure at each stage, and other companies might succeed first.

To decide whether to invest, firms weigh their expected costs against potential rewards. If successful, they'll receive the incentive payment — but they might have to share it with other successful developers. If they fail, they bear all the costs with no return.

Our framework captures this decision-making process. We look at:
<ul>
    <li>The full development costs, from research through commercialization </li>
    <li>The probability of success at each stage </li>
    <li>The time value of money between when costs are incurred and payments are received </li>
    <li>The impact of competition on expected returns </li>
</ul>

From the funder’s perspective, the optimal size of the pull mechanism depends on the number of firms they want to entice to invest in the target innovation. Hence, our model captures the estimated number of firms that a funder would expect to invest based on the size of the incentive offered.

To make this analysis tractable, we make some simplifying assumptions:
<ul>
    <li>All firms are rational and risk-neutral: they participate only if expected benefits exceed costs. </li>
    <li>Firms face one choice: whether to invest in a single innovation attempt. All firms make this decision and make progress on research on the same timetable. </li>
    <li>All innovation attempts are identical and independent.</li>
    <li>Successful firms share the reward equally.</li>
    <li>Benefits do not depend on the number of successful firms. The goal of the funder is to ensure at least one firm is successful. </li>
</ul>

*Note: Throughout this post, we use "firm" to refer to any profit-motivated innovator - whether a large company, research institution, startup, or university spinoff.*

<h2 id="understanding_costs">3. Understanding Innovation Costs and Risks</h2>
<h3 id="key_components">Key components</h3>
First, we need to understand the costs and risks that firms incur when trying to innovate. The higher the cost of innovation, the larger the pull size needs to be in order for firms to find investing in innovation worthwhile. Account for the following elements:

**i. Cost of R&D and commercialization.** This category includes the fixed and marginal costs to a firm to invent, produce, and deliver the desired product. Costs associated with identifying promising leads, validating their efficacy, testing their safety, shepherding through regulatory approval, manufacturing, marketing, and distributing the final good all fall under this category. 

<button class="see-more-btn" onclick="toggleDetails('rdcosts-details')">Show example</button>
<div id="rdcosts-details" class="details-box">
    <p>
    For example, consider an AMC to incentivize the development of a livestock vaccine. We can use past data on livestock vaccine innovations to inform our estimates on the cost of development. The following comes from a 2014 paper estimating the costs to develop a vaccine for chicken in 2009. Any forward-looking estimates would need to adjust for inflation.
</p>

<table>
    <thead>
        <tr>
            <th>Phase</th>
            <th>Duration (Years)</th>
            <th>Reported Cost (1000 €)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Research and Development</td>
            <td>3</td>
            <td>1,949</td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>1</td>
            <td>137</td>
        </tr>
        <tr>
            <td>Testing</td>
            <td>2</td>
            <td>208</td>
        </tr>
        <tr>
            <td>Approval</td>
            <td>1</td>
            <td>48</td>
        </tr>
    </tbody>
</table>


<p>
    Data from Jensen, J. D., Lund, M., & Fabricius, O. (2014). Economic analysis of developing a Campylobacter vaccine to poultry: a real options approach. Frederiksberg: Department of Food and Resource Economics, University of Copenhagen. <i>IFRO Report, No. 227</i>.
</p>

<p>
    All-in costs would also need to factor in the cost of building a production facility, marketing, and distribution.
</p>

</div>


**ii. Likelihood of technological success.** Innovation is inherently risky. There is no guarantee that firms that incur R&D and commercialization costs will succeed in developing an innovation and bringing it to market. The probability of success includes a firm's risk of technological failure such that they are unable to fulfill the terms of the technical product parameters. 

<button class="see-more-btn" onclick="toggleDetails('rdsuccess-details')">Show example</button>
<div id="rdsuccess-details" class="details-box">

Using the same data as before, we can assign probabilities to each step. 
<br>
<table>
    <thead>
        <tr>
            <th>Phase</th>
            <th>Duration (Years)</th>
            <th>Reported Cost (1000 €)</th>
            <th>Unconditional Probability of Success </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Research and Development</td>
            <td>3</td>
            <td>1,949 </td>
            <td>20% </td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>1</td>
            <td>137</td>
            <td>75% </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>2</td>
            <td>208</td>
            <td>20% </td>
        </tr>
        <tr>
            <td>Approval</td>
            <td>1</td>
            <td>48</td>
            <td>90%</td>
        </tr>
    </tbody>
</table>

Since estimates of success rates vary substantially, designers should be careful that the data source for success rates and costs are the same. Some sources may estimate a higher success rate, because they are excluding earlier stages. Or they may estimate the success rate of an entire research program, which includes multiple concurrent attempts, resulting in both a higher success rate but also a higher cost. These alternative approaches are not wrong, but one needs to be careful that the costs and success rates are coming from the same source.

</div>

**iii. Firm’s hurdle rate of return.** Firms expect to make a profit and, all else equal, prefer investments that pay money today rather than in the future. Since AMCs and other pull mechanisms require firms to spend money in the present on the possibility of receiving funds in the future, funders need to compensate firms for that delay. In general, the more a funder wishes to delay funding, the greater the premium the funder must pay to induce entry. MSA currently uses annual discount rates of 8-10%, depending on the sector involved. For long-dated AMCs, i.e. AMCs for technological innovations that may take ten years or more to pay off, including hurdle rates can more than double nominal costs.

<button class="see-more-btn" onclick="toggleDetails('discountratesizing-details')">How discounting affects AMC sizing</button>
<div id="discountratesizing-details" class="details-box">

In general, the more the funder delays payments, the larger the nominal payments need to be to compensate firms for that delay. Of note, hurdle rates tend to substantially exceed social discount rates, so the real value of the needed pull size will also rise as the delays grow. 

Suppose, a firm has a 10% hurdle rate, while the funder has a discount rate of 3%. If the payout is delayed ten years, then the funder will need to pay \$259 in year 10 to induce \$100 in private spending in year 0. 


  <table>
    <thead>
        <tr>
            <th>Payout Year</th>
            <th>0</th>
            <th>5</th>
            <th>10</th>
            <th>15</th>
            <th>20 </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Future payout needed for firms to have net present value &gt; 0</td>
            <td>100</td>
            <td>161</td>
            <td>259</td>
            <td>418</td>
            <td>673 </td>
        </tr>
        <tr>
            <td>Funder&#39;s present value of payout</td>
            <td>100</td>
            <td>139</td>
            <td>193</td>
            <td>268</td>
            <td>372</td>
        </tr>
    </tbody>
</table>

Formally, if $r$ is the firm hurdle rate and $t$ is the number of years between upfront payment, the nominal value of  the pull commitment to induce \$1 in spending is $$(1+r)^t$$. 

 <div style = "text-align: left;">
    <embed style="border: none;" src="./time_penalty.html" dpi="300" width="105%" height="800px" />
  </div>

</div>

<h3 id="expected_costs">Calculating Firms' Expected Costs</h3>

Innovation requires multiple steps, including research and development, testing, trials, and regulatory approval. Each step incurs its own set of costs, and its own risks of failure. However, when sizing, it is important to remember that firms do not incur these costs all at once. Instead, if the project fails at any specific step, the firm simply stops and does not incur the costs of the subsequent stages. Instead, when sizing, one needs to calculate the expected cost at the time of entry, properly discounted by time.


<button class="see-more-btn" onclick="toggleDetails('optionvalue-details')">Walking through an example</button>
<div id="optionvalue-details" class="details-box">

Development is a often staged process where you can bow out with any adverse result (but you cannot see the success of other firms), let us say the following: k is the number of innovation steps, and P is a vector representing the probability of success at reaching the next stage where $P = \{p_0,p_1,p_2, ... , p_k\}$. Reaching stage 1 has probability 1 so $p_0=1$. Let $C$ be a vector representing the cost at each stage $C = \{c_0,c_1,c_2, ... , c_k\}$. Initialization cost is 0 for $c_0=0$. 

Without consideration of the time value of money, the cost of development is $$\sum_{i=1}^{k} c_i \prod_{j=1}^{i} p_{j-1}$$.



Consider the case of the vaccine considered previously. We first need to decompose into annual costs and probabilities of failure so we can calculate expected costs.

<table>
    <thead>
        <tr>
            <th>Phase</th>
            <th>Reported Cost (1000 €)</th>
            <th>Cost (2024 1000 $)</th>
            <th>Unconditional Probability of Success</th>
            <th>Probability of reaching step</th>
            <th>Expected Cost (1000 $) </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>R&amp;D</td>
            <td>649.7</td>
            <td>955</td>
            <td>58.40%</td>
            <td>100%</td>
            <td>955 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>649.7</td>
            <td>955</td>
            <td>58.40%</td>
            <td>58.40%</td>
            <td>554 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>649.7</td>
            <td>955</td>
            <td>58.40%</td>
            <td>34.10%</td>
            <td>321 </td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>137</td>
            <td>201</td>
            <td>75%</td>
            <td>19.50%</td>
            <td>39 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>104</td>
            <td>153</td>
            <td>44.70%</td>
            <td>14.60%</td>
            <td>22 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>104</td>
            <td>153</td>
            <td>44.70%</td>
            <td>6.60%</td>
            <td>10 </td>
        </tr>
        <tr>
            <td>Approval</td>
            <td>48</td>
            <td>71</td>
            <td>90%</td>
            <td>3.00%</td>
            <td>2 </td>
        </tr>
        <tr>
            <td>Release</td>
            <td>-</td>
            <td>-</td>
            <td>100%</td>
            <td>2.70%</td>
            <td>-</td>
        </tr>
    </tbody>
</table>


While the all-in cost of running from start to finish is \$3.4 million, because the innovator can stop whenever they fail, the expected cost at time of initiation is only \$1.9 million.

We now need to introduce the time value of money. Discounting reduces future costs, as firms value expenses incurred in the future less than they value expenses they incur in the present. For example, if we use an 8.05% discount rate (from <a href="https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/wacc.html" target="_blank" rel="noopener noreferrer">Damadoran 2024</a>), we get the following table for our livestock vaccine modeling.
, we get the following table for our livestock vaccine modeling.


  <table>
    <thead>
        <tr>
            <th>Phase</th>
            <th>Cost (2024 1000 $)</th>
            <th>Unconditional Probability of Success</th>
            <th>Probability of reaching step</th>
            <th>Expected Cost (1000 $)</th>
            <th>Discounted Present Value  </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>R&amp;D</td>
            <td>955</td>
            <td>58.40%</td>
            <td>100%</td>
            <td>955</td>
            <td>955 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>955</td>
            <td>58.40%</td>
            <td>58.40%</td>
            <td>554</td>
            <td>513 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>955</td>
            <td>58.40%</td>
            <td>34.10%</td>
            <td>321</td>
            <td>275 </td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>201</td>
            <td>75%</td>
            <td>19.50%</td>
            <td>39</td>
            <td>31 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>153</td>
            <td>44.70%</td>
            <td>14.60%</td>
            <td>22</td>
            <td>16 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>153</td>
            <td>44.70%</td>
            <td>6.60%</td>
            <td>10</td>
            <td>7 </td>
        </tr>
        <tr>
            <td>Approval</td>
            <td>71</td>
            <td>90%</td>
            <td>3.00%</td>
            <td>2</td>
            <td>1.3 </td>
        </tr>
        <tr>
            <td>Release</td>
            <td>-</td>
            <td>100%</td>
            <td>2.70%</td>
            <td>-</td>
            <td>0 </td>
        </tr>
        <tr>
            <td>Sum</td>
            <td>3,443</td>
            <td>-</td>
            <td>-</td>
            <td>1,904</td>
            <td>1,799</td>
        </tr>
    </tbody>
</table>

Since the overwhelming majority of the costs fall in the first few years, discounting only reduces all-in costs from \$1.9 million to \$1.8 million. For human vaccines, where Stage III trials can get extremely expensive, this discounting can have a major effect on the present value of the incentive.
</div>

<h3 id="sourcing_parameters">Sourcing Parameter Estimates</h3> 
Data on the costs and risks of innovation can be difficult to know, but there are several types of sources we have found useful for information gathering:
<ul>
    <li>Academic literature and industry reports provide historical cost averages </li>
    <li>Government and regulatory filings often contain detailed development costs </li>
    <li>Interviews with industry veterans who can validate cost assumptions</li>
    <li>Similar completed projects provide comparable reference points</li>
</ul>

When using these sources, it's important to be aware of their potential limitations and biases. Published costs often represent successful attempts only. They may also be dated and need adjustment for inflation. Additionally, costs can vary significantly by sector, region, and specific technical challenges. Triangulating between multiple sources can provide a more complete picture.


Additionally, remember that we're trying to identify the threshold case — the point at which firms are just willing to participate. Firms with lower costs or higher probabilities of success than our estimates will find participation attractive, while those with higher costs or lower chances of success will not participate.

<h2 id="program_size">4. Determining the Overall Program Size</h2>

We have seen how to calculate the expected costs firms face when pursuing innovation, but how do we move from understanding a single firm's costs to determining the total size of the pull incentive needed?

<h3 id="number_of_attempts">Target Number of Attempts</h3>

The key is to recognize that each additional firm attempting innovation increases the overall chances of success. Consider a case where any single firm has a 10% chance of developing a successful innovation. With multiple firms participating, our chances of success improve, though attracting additional firms becomes increasingly expensive as they must consider sharing the reward if multiple succeed.

This creates a fundamental tradeoff: the more firms that participate, the more likely we are to achieve the innovation's benefits—whether that's lives saved from a new vaccine or emissions reduced from clean technology—but increasing this probability becomes increasingly expensive. Setting a target probability of success means asking: what is the social value of increasing our chances of achieving these benefits? During the COVID-19 pandemic, the massive daily cost of delay meant even small increases in the probability of success had enormous value, justifying efforts to attract many firms ([Ahuja et al 2021](https://www.aeaweb.org/articles?id=10.1257/pandp.20211103)). However, this contrasts with other pull funding use cases where the funder only seeks to incentivize a few of the best-suited firms to participate.

Thinking through how many firms are likely to be attracted to compete for the pull mechanism, or we want to see compete, is a key ingredient in the costing analysis.

<iframe 
    src="needed_attempts_graph.html" 
    width="100%" 
    height="600" 
    style="border: none;">
</iframe>

<button class="see-more-btn" onclick="toggleDetails('needed-attempts-math')">Show math</button>
<div id="needed-attempts-math" class="details-box">
    We make the following assumpions, many of which will be later relaxed.
    <br>
    <br>
    <ol>
    <li>All firms are risk-neutral and identical ex ante.</li>
    <li>Firms face one choice: whether to commit a single innovation attempt. Although firms enter sequentially, all research progresses on the same timetable.</li>
    <li>All innovation attempts are identical and independent.</li>
    <li>If multiple firms succeed, they split the reward equally. For example, if one firm succeeds, that firm receives the entire prize $X$, while two successful firms would each receive $\frac{1}{2}X$. </li>
    </ol>
    <table>
    <thead>
        <tr>
            <th>Variable Name</th>
            <th>Description </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$\theta$</td>
            <td>Target probability of success </td>
        </tr>
        <tr>
            <td>$n$</td>
            <td>Number of attempts </td>
        </tr>
        <tr>
            <td>$p$</td>
            <td>Per-attempt probability of success</td>
        </tr>
        <tr>
            <td>$X$</td>
            <td>Present value of pull incentive</td>
        </tr>
        <tr>
            <td>$\mathbb{E}[c]$</td>
            <td>Present value of expected cost per innovation attempt</td>
        </tr>
    </tbody>
    </table>
<!-- -->
    Suppose we want to create a pull mechanism such that the probability of success of at least one firm is at least $\theta$. In other words, need to find an $n$ such that $1 - (1-p)^n \geq \theta$. Through simple re-arrangement, we can find that: 
<!-- -->
    $$ n \geq \frac{ln(1-\theta)}{ln(1-p)} $$
<!-- -->
    If the number of entrants exceeds that value, then the probability of success will exceed that target. As all firms are identical in all respects, the probability of receivng the reward conditional on entering is equal to the probability that any firm succeeds, divided by the number of firms entering. In other words, 
<!-- -->
    $$ \mathbb{P}(win|entry) = \frac{1-(1-p)^n}{n} $$
<!-- -->
    A firm will only enter if its expected revenue exceeds the expected costs ($\mathbb{E}[c]$). For a risk-neutral firm, the expected revenue is simply $\mathbb{P}(win|entry) \cdot X$. As a result, by plugging in the values for $\mathbb{P}(win|entry)$ and $n$ we found above, we find that the needed pull size becomes 
<!-- -->
    $$ X \geq \frac{ln(1-\theta)}{\theta \cdot ln(1-p)} \cdot \mathbb{E}[c]$$
 <!-- -->
    Future sections will relax some of these assumptions and build out a complete model.
</div>

The more firms that have already entered, the higher the marginal cost to induce an extra firm, because now firms face higher risk of splitting the prize. As the number of firms increases, the marginal cost approaches the cost of each additional attempt. For instance, if the probability of success per attempt is 5% and the present value cost of each attempt is \\$1,000,000 then a funder would need to increase the pull size by \\$580,000 to move from nine to ten attempts . In contrast, moving from 50 to 51 attempts requires an additional marginal cost of \$856,000.

<iframe 
    src="marginal_cost_to_induce_entry.html" 
    width="100%" 
    height="600" 
    style="border: none;">
</iframe>

<button class="see-more-btn" onclick="toggleDetails('marginal-cost-entrant')">Show math</button>
<div id="marginal-cost-entrant" class="details-box">
    <table>
    <thead>
        <tr>
            <th>Variable Name</th>
            <th>Description </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$n$</td>
            <td>Number of attempts </td>
        </tr>
        <tr>
            <td>$p$</td>
            <td>Per-attempt probability of success</td>
        </tr>
        <tr>
            <td>$X$</td>
            <td>Present value of pull incentive</td>
        </tr>
        <tr>
            <td>$\mathbb{E}[c]$</td>
            <td>Present value of expected cost per innovation attempt</td>
        </tr>
    </tbody>
    </table>

    From the previous section, we know that $X \cdot \frac{1-(1-p)^n}{n} \geq \mathbb{E}[c]$. Through re-arrangement we can find that
    $$ X \geq \frac{n \cdot \mathbb{E}[c]}{1-(1-p)^n}$$

    We need to simply take the derivative of that expression to find $\frac{\mathrm{d}X}{\mathrm{d}n}$, which we find as

    $$\frac{\mathrm{d}X}{\mathrm{d}n}= \mathbb{E}[c] \cdot \frac{1-(1-p)^n + n \cdot (1-p)^n \cdot ln(1-p)}{(1-(1-p)^n)^2}$$

    $$ lim_{n \to \infty}(\frac{\mathrm{d}X}{\mathrm{d}n}) = \mathbb{E}[c] $$


</div>

Putting all of these components together, we can calculate the needed pull size in order to induce entry. The following graph shows the needed pull size as a function of the multiple of the cost of innovation in term of the firm’s own discount rate. That discount rate is crucial: as we saw in the previous section, the nominal value will be far higher if revenues are delayed substantially. For example, if an innovation attempt costs \\$1 million, then the present value of the incentive needs to be at least \\$66 million to get at least an 80% chance of success. If the payments occurred ten years (a realistic timeframe for novel drugs or vaccines), then the nominal of the incentive will have to be at least \\$142 million. 
 


<iframe 
    src="simple_sizing_graph.html" 
    width="100%" 
    height="650" 
    style="border: none;">
</iframe>





<button class="see-more-btn" onclick="toggleDetails('simple-details')">Show math</button>
<div id="simple-details" class="details-box">
    <table>
    <thead>
        <tr>
            <th>Variable Name</th>
            <th>Description </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$\theta$</td>
            <td>Target probability of success</td>
        </tr>
        <tr>
            <td>$n$</td>
            <td>Number of attempts </td>
        </tr>
        <tr>
            <td>$p$</td>
            <td>Per-attempt probability of success</td>
        </tr>
        <tr>
            <td>$\mathbb{E}[c]$</td>
            <td>Present value of expected cost per innovation attempt</td>
        </tr>
    </tbody>
    </table>
    $$ \text{Present value of pull size} \geq \frac{\ln(1 - \theta)}{\theta \cdot \ln(1 - p)} \cdot \mathbb{E}[c] $$
</div>

*Note: The expected cost of an attempt (used when considering firm participation) can be substantially lower than the full actualized development costs. For instance, if full development costs are $20 million but have only a 5% chance of being incurred, the expected cost is \\$1 million, as stated in the example above. This is one of the reasons pull mechanisms appear very large relative to expected costs.*


<h3 id="other-considerations">Other Considerations</h3>

<h4 id="pipeline">Within and across firm attempts: pipeline approaches to innovation</h4>

The above analysis assumes a competitive market where each firm makes a single attempt. However, this assumption may be rather unrealistic, as the market may only have a finite number of firms capable of responding to the incentive. Suppose research trials have a 2% success rate and a pull designer desires a 50% probability of at least one success: the above formula suggests that the funder now needs to incentivize at least 35 attempts. But there may not be 35 firms capable of responding to the incentive.

As a result, we consider how the model changes if one imposes constraints on the number of firms that are capable of responding. Intuitively, this restriction requires firms to initiate multiple attempts each. The marginal cost to the funder to induce that additional attempt will be higher than under the previous one-attempt-per-firm model as a firm now faces a risk of self-competition. Intuitively, the fewer possible firms in the market, the greater the premium the funder must pay. 

<button class="see-more-btn" onclick="toggleDetails('monopoly-constraints')">Show math</button>
<div id="monopoly-constraints" class="details-box">

<table>
    <thead>
        <tr>
            <th>Variable Name</th>
            <th>Description </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$\theta$</td>
            <td>Target probability of success </td>
        </tr>
        <tr>
            <td>$n$</td>
            <td>Number of attempts </td>
        </tr>
        <tr>
            <td>$p$</td>
            <td>Per-attempt probability of success</td>
        </tr>
        <tr>
            <td>$X$</td>
            <td>Present value of pull incentive</td>
        </tr>
        <tr>
            <td>$\mathbb{E}[c]$</td>
            <td>Present value of expected cost per innovation attempt</td>
        </tr>
    </tbody>
</table>

Consider an extreme case of a monopoly firm. The monopolist receives no additional reward for having multiple successes. As a result, a marginal attempt is only valuable when all other attempts fail (with probability $(1-p)^{n-1}$), but that one additional attempt succeeds (with probability $p$). Thus, we get the value equation of

$$ X \cdot p \cdot (1-p)^{n-1} \geq \mathbb{E}[c]$$

The number of attempts needed to achieve at least a $\theta$ probability of success does not change. As a result, we plug $n \geq \frac{ln(1-\theta)}{ln(1-p)}$ into the above equation, producing:

$$ X \geq \frac{1-p}{p \cdot (1-\theta)} \cdot \mathbb{E}[c]$$

We can see that for all $\theta > p$, the needed pull size for a monopolist exceeds the pull size for a competitive market (when $\theta \leq p$, one only needs to induce one attempt so the two cases are identical).
<br>
<br>
In reality, neither a monopolist nor a perfectly fragmented market is likely. Some in-between world is far more probable. The extent of the premium rapidly declines as the number of firms increases. The following section details the math, though one is encouraged to skip to the charts and tables for the intuition.

Assume $k$ firms in the market. Because of the homogeneity assumption, each firm will now undertake $\frac{n}{k}$ attempts. Let us now define $\mathbb{V}(X,k)$ as the present value of the pull size given the number of firms in the market. 

$$ V(X,k) \cdot p \cdot (1-p)^{\frac{n}{k} - 1} \geq \mathbb{E}[c]$$

In the above, a firm's marginal additional attempt is only valuable if the marginal attempt succeeds ($p$) and all other attempts by that firm ($(1-p)^{\frac{n}{k}-1}$) fails.

$$\mathbb{V}(X, k) = \sum_{i=0}^{k-1} \frac{1}{i+1} \cdot \mathbb{P}(\text{successes} = i) \cdot X $$

In other words, thev value of winning depends on the number of other firms that are successful. The term $\frac{1}{i+1}$ represents the share of $X$ received by the firm given $i$ other successful firms.

$$\mathbb{P}(\text{successes} = i) = \binom{k-1}{i} \cdot \left(1 - (1-p)^{\frac{n}{k}}\right)^i \cdot \left((1-p)^{\frac{n}{k}}\right)^{k-1-i}$$

The above equation is simply an expansion of the binomial formula where the number of attempts per firm is $\frac{n}{k}$ and is equivalent to calculating the probability of any specific number of heads when one flips a weighted coin $k-1$ times when the probability of any given flip resolving as heads if $(1-p)^{\frac{n}{k}}$. In cases where the number of attempts is not divisible by the number of firms, we split proportionately. For example, if there are 27 desired attempts and only five firms, three firms will conduct five attempts each, while two firms will conduct six.

In practice, this approach results in a higher needed pull size than the “one attempt per firm” model, but a lower pull size than the monopolist case. Intuitively, the more attempts per firm, the larger the price premium grows. That said, the result tails off so quickly after the monopolist case that this factor is rarely worth considering. For example, if the probability of success per attempt was 6% and the target probability was 50%, having only four firms results in a pull size 8.8% larger than if there were enough firms to have one attempt per firm, but 25% cheaper than if there were only a single firm. However, if the target probability was 66.67% instead, a four firm world requires a 15.8% premium over the one-firm-per-attempt, but a 59.3% discount from a monopolist situation. 

 <div style = "text-align: left;">
    <embed style="border: none;" src="./number_of_firms_sizing.html" dpi="300" width="100%" height="800px" />
  </div>

</div>

<h4 id="correlation-section">Correlated probabilities of success</h4>

The above analysis assumes that all attempts are independent, akin to flipping a coin. Given enough attempts, the probability of a successful innovation approaches 100%. But this assumption is transparently unrealistic for two reasons. First, the innovation itself may be impossible (or at least impossible in the near future). No amount of separate attempts would allow ancient Roman scientists to construct a modern computer. Second, individual firms may have idiosyncratic failure modes. For instance, they may choose the wrong path or have ill-suited personnel, etc. Unfortunately, the level of correlation between attempts is unobservable, and designers should use their discretion to incorporate this factor.  In general, considering correlation between attempts will raise costs, generally on the magnitude of 10-50%. 

<button class="see-more-btn" onclick="toggleDetails('correlation')">Show math</button>
<div id="correlation" class="details-box">
<table>
    <thead>
        <tr>
            <th>Variable Name</th>
            <th>Description </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$\theta$</td>
            <td>Target probability of success </td>
        </tr>
        <tr>
            <td>$n$</td>
            <td>Number of attempts </td>
        </tr>
        <tr>
            <td>$p$</td>
            <td>Per-attempt probability of success</td>
        </tr>
        <tr>
            <td>$X$</td>
            <td>Present value of pull incentive</td>
        </tr>
        <tr>
            <td>$\mathbb{E}[c]$</td>
            <td>Present value of expected cost per innovation attempt</td>
        </tr>
        <tr>
            <td>$\eta$</td>
            <td>Global possibility parameter</td>
        </tr>
        <tr>
            <td>$\gamma$</td>
            <td>In-firm possibility parameter</td>
        </tr>
        <tr>
            <td>$m$</td>
            <td>Number of attempts per firm</td>
        </tr>
    </tbody>
</table>

We can thus introduce two sources of correlation: a global parameter that reflects the maximum probability of success given an arbitrarily large number of firms and attempts, and a local parameter that reflects the possibility that any given firm could possibly succeed.

In practice, introducing this two-stage correlation structure has two effects on the total pull size: 1) the marginal cost of increasing the target probability of success rises dramatically and 2) the marginal cost for having a concentrated market with few firms rises concurrently. 

In the following equations, let  represent the global possibility parameter and  be the intra-firm possibility parameter. m is the number of attempts per firm.

Set aside the global parameter for now and let us focus our efforts on the within-firm possibility parameter $\gamma$. 

$$\mathbb{P}_{firm}(success \geq 1) = \gamma \cdot (1-(1-p)^m) $$

The probability that all of a firm's attempts fail is the sum of the probability that the approach is fundamentally infeasible ($1 - \gamma$) and the probability that the approach is feasible ($\gamma$) but all of the attempts fail regardless ($(1-p)^m$). Putting together, one gets $\mathbb{P}_{firm}(success \geq 1) = 1 - [(1-\gamma) + \gamma \cdot (1-p)^m]$, which simplifies to Equation 4.1.

Now to introduce the global possibility parameter $\eta$.

$$\mathbb{P}_{all}(success \geq 1) = \eta \cdot (1 - [1-\gamma \cdot (1-(1-p)^m)]^k) \geq \theta$$

The goal is to get the probability of success to exceed the target threshold. With the new global possibility parameter, the probability that at least one firm succeeds is the probability that any given firm succeeds conditional on the innovation being possible (from Equation 4.1) multiplied by the possibility $\eta$ that the innovation is at all possible.

$$m \geq \frac{ln(1-\frac{1-(1-\frac{\theta}{\eta})^{\frac{1}{k}}}{\gamma})}{ln(1-p)}$$

Algebraic rearrangement of the second equation produces the third. There is no simplified form for the necessary pull size. Instead, one can insert the value of $m$ into the equation for the finite firms, replacing the $\frac{n}{k}$ term that represnts attempts per firm with the value for $m$ found in Equation 4.3.

In practice, introducing correlation substantially increases the needed pull size as well, as he number of attempts needed to reach the same probability of success increases dramatically. 
</div>

<iframe 
    src="complete_sizing_graph.html" 
    width="100%" 
    height="800" 
    style="border: none;">
</iframe>

<h2 id="total_costs">5. Total Costs and Cost Effectiveness</h2>

<h3 id="additional_costs">Additional Cost Considerations</h3>

<ul>
    <li><strong>Monitoring and verification.</strong> Pull mechanisms involve paying for outcomes and outputs. This often requires being able to monitor outcomes and outputs (e.g. verifying sales, adoption, impact on outcome measures). In some cases, these costs will be significant and should be considered as part of the overall costs of the program in addition to the direct cost of the pull fund. </li>
    <li><strong>Costs of designing and implementing the pull fund.</strong> The institution designing and implementing the pull funding program will incur personel, administrative, and overhead costs. These are likely to be orders of magnitude smaller than the cost of incentivizing innovation. </li>
    <li><strong>Third-party purchases. </strong> Innovations will differ in the extent to which the funder will need to make up the whole market. For some innovations, there will be significant private demand which can be subtracted from the overall market size to calculate the size of the pull fund needed.  Purchases from other agents are not part of the cost to the funder. However, costs paid by other agents that would be unlikely to occur in the absence of the pull mechanism should be considered when appraising the benefits and costs of the intervention. </li>
</ul>
 

<h3 id="cost_effectiveness">Cost Effectiveness</h3>
To determine the overall cost-effectiveness of a pull mechanism, compare the total costs to a separate, rigorous assessment of the expected benefits of the target innovation. 

Pull mechanism are unique investment opportunities in that funders either receive the social return of successful innovation or, should no firm succeed at innovation, the chance to spend their funds on other opportunities at a later date. The money is not lost even if no innovation is ultimately successful.

Two useful metrics for considering cost-effectiveness are the benefit-cost ratio and net present value of the project.

The Benefit Cost Ratio (BCR) provides a clear indication of the value generated per dollar spent by dividing the expected benefits by the total costs. A BCR greater than 1 signals that the benefits outweigh the costs, demonstrating the intervention's cost-effectiveness.

<button class="see-more-btn" onclick="toggleDetails('bcr-details')">Show BCR Equation</button>
<div id="bcr-details" class="details-box">
    <table>
        <thead>
            <tr>
                <th>Variable Name</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>$p$</td>
                <td>Probability that at least one firm succeeds at innovation</td>
            </tr>
            <tr>
                <td>$B$</td>
                <td>Benefits if the innovation succeeds</td>
            </tr>
            <tr>
                <td>$F$</td>
                <td>Funder's budget</td>
            </tr>
            <tr>
                <td>$\gamma$</td>
                <td>Social ROI of the funder's marginal alternate investment opportunity</td>
            </tr>
        </tbody>
    </table>
    <strong>Benefit-Cost Ratio (BCR):</strong>
    $$ \text{BCR} = \frac{p \cdot B + (1 - p) \cdot F \cdot \gamma}{F} $$

</div>

The Net Present Value directly quantifies the net societal value created by the pull mechanism, accounting for the time value of money. A positive NPV indicates the intervention generates a net gain for society. To calculate overall net present value teams should multiple the probability of program success by the difference of the present value of benefits and costs

<button class="see-more-btn" onclick="toggleDetails('npv-details')">Show BCR Equation</button>
<div id="npv-details" class="details-box">
    <table>
        <thead>
            <tr>
                <th>Variable Name</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>$p$</td>
                <td>Probability that at least one firm succeeds at innovation</td>
            </tr>
        </tbody>
    </table>
    <strong>Net Present Value (NPV):</strong>
    $$ \text{NPV} = p \cdot (\text{Present Value of Benefits} - \text{Present Value of Costs}) $$

</div>

Together, the BCR and NPV provide a balanced assessment of the pull mechanism's cost-effectiveness. This allows funders to make informed decisions about whether to proceed with the investment and how to optimize the target probability of success for maximum impact.

---

William Arnesen & Claire McMahon, 2024

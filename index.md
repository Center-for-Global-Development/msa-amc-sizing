---
layout: default
title: A Practical Guide to Sizing Innovation Incentives
---
<link rel="stylesheet" href="style.css">

<meta name="viewport" content="width=device-width, initial-scale=1.0">


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

<script>
    function toggleSidebar() {
      const sidebar = document.getElementById('sidebar');
      // Toggle 'sidebar-hidden' class on each click
      if (sidebar.classList.contains('sidebar-hidden')) {
        sidebar.classList.remove('sidebar-hidden');
      } else {
        sidebar.classList.add('sidebar-hidden');
      }
    }
  </script>

<button class="hamburger-btn" onclick="toggleSidebar()">☰ Menu</button>

<nav class="sidebar sidebar-hidden" id="sidebar">
        <ol class="nav-list">
            <li><a href="#introduction">Introduction</a></li>
            <li>
                <a href="#conceptual_framework">Conceptual Framework</a>
                <ol>
                    <li><a href="#firm_decision_making">Firm Decision Making</a></li>
                    <li><a href="#model_setup">Model Setup</a></li>
                </ol>
            </li>
            <li>
                <a href="#understanding_costs">Understanding Innovation Costs and Risks</a>
                <ol>
                    <li><a href="#key_components">Key Components</a></li>
                    <li><a href="#expected_costs">Calculating Firms' Expected Costs</a></li>
                    <li><a href="#sourcing_parameters">Sourcing Parameter Estimates</a></li>
                </ol>
            </li>
            <li><a href="#program_size">Determining the Overall Program Size</a>
                <ol> 
                    <li><a href="#simplest_version">Simplest Version</a></li>
                    <li><a href="#number_of_attempts">Target Number of Attempts</a></li>
                    <li><a href="#cost_of_multiple_attempts">The Cost of Incentivizing Multiple Attempts</a></li>
                </ol>
            </li>
            <li><a href="#total_costs">Total Costs and Cost Effectiveness</a>
                <ol>
                <li><a href="#additional_costs">Additional Cost Considerations</a></li>
                <li><a href="#cost_effectiveness">Cost Effectiveness</a></li>
                </ol>
            </li>
            <li><a href="#conclusion">Conclusion</a></li>
            <li><a href="#appendix">Appendix A: Beyond the Simple Model</a>
                    <ol>
                        <li><a href="#pipeline">Within and Across Firm Attempts</a></li>
                        <li><a href="#correlation-section">Correlated Probabilities</a></li>
                        <li><a href="#subsidy-passthrough-section">Competition & Subsidy Passthrough</a></li>
                     </ol>
            </li>
            <li><a href="#complete_example">Appendix B: A Complete Example</a></li>
        </ol>
</nav>

--

<h4> Contributing authors: William Arnesen & Claire McMahon, 2025 </h4>

---

<div class="takeaways-box">
    <h3> KEY TAKEAWAYS</h3>
    <ol>
        <li>When designing pull funding mechanisms, determining the right incentive size is critical. Larger incentives attract more firms and increase the chances of success, but too large an incentive wastes funds that could be used for other projects. This guide provides a practical framework for making this decision.</li>
        <li>The incentive size needed to motivate firm participation depends on:</li>
            <ol type="i">
                <li><strong>Development costs:</strong> Firms face expenses including R&D, testing, regulatory approval, and commercialization, all adjusted for the probability of failure at each stage.</li>
                <li><strong>Innovation risk</strong>: More technologically distant innovations require larger incentives to compensate firms for the high likelihood of R&D failure. </li>
                <li><strong>The time value of money</strong>: Firms discount future returns, and long development timelines for major innovations reduce the present value of potential rewards.</li>
            </ol>
        <li>The <strong>social value of the innovation</strong> sets an upper limit on willingness to pay and helps for prioritizing funding opportunities.</li>
        <li>While total funding commitments for pull mechanisms often appear large, they reflect that firms must bear both the risks of development failure and the opportunity costs of capital over long development timelines. Understanding these components helps funders right-size their commitments.</li>
    </ol>
</div>

<h2 id="introduction">1. Introduction</h2>


Funders using pull mechanisms face a crucial practical question: how large of an incentive should they offer? This guide provides a practical framework for answering that question, breaking down the  factors that determine the incentive size needed to attract serious development efforts and how to optimize that size.

<span class="tooltip-word">Pull mechanisms<span class="tooltip-text">"Pull funding" is incentive-based funding that rewards firms after achieving specific results or delivering a successful product. Since funders do not pay upfront, pull mechanisms place risk of technological success on the innovators.</span></span>, such as prizes and <span class = "tooltip-word">advance market commitments<span class="tooltip-text">Advanced market commitments are agreements where governments or organizations commit to purchasing or subsidizing a product once it is successfully developed, guaranteeing a market for manufacturers.</span></span> (AMCs), reward success rather than funding research upfront. They shift the burden of innovation risk and cost onto the innovator, who only gets paid when specific goals are achieved. Getting the size of the reward right is critical: too small, and firms won’t enter; too large, and the program wastes scarce funds.

In this guide, we outline a practical approach for using estimates of development costs, technical risks, and market dynamics to gauge how much pull funding might be needed to motivate firms to pursue socially valuable innovations. This framework is a first-step, order-of-magnitude tool—particularly useful at the outset of a project, when funders are considering whether a pull mechanism could be viable, estimating the scale of funding needed, or determining what kind of institution (e.g., a philanthropic funder or a government agency) might be suited to support the effort. This methodology is especially well-suited to innovations that proceed in discrete stages, where development risks and costs can be estimated using available information.

Our approach draws from our experience evaluating pull mechanisms across sectors and builds on academic work by <a href="https://www.aeaweb.org/articles?id=10.1257/pandp.20211103">Ahuja et. al 2021</a> and <a href="https://pubsonline.informs.org/doi/10.1287/mnsc.2021.4163">Kremer, Levin and Snyder 2022 </a>, among others. While grounded in theory, this is not an academic paper; it’s a practical explainer of our current best practices at the Market Shaping Accelerator. While not exhaustive, the guide also includes an appendix with additional complexities and refinements we’ve found helpful in real-world contexts. We continue to evolve this work and welcome feedback from funders, designers, and researchers tackling similar challenges.

The sections that follow break the sizing challenge into manageable steps: starting with defining a conceptual framework (<a href="#conceptual_framework">Section 2</a>), then estimating innovation costs and risks  (<a href="#understanding_costs">Section 3</a>), calculating the incentive size needed for a desired chance of success (<a href="program_size">Section 4</a>), and assessing total program costs and cost-effectiveness (<a href="total_costs">Section 5</a>). The appendix provides a full <a href="#complete_example">case study</a>  for methane-reducing livestock vaccines and extensions for more complex modeling scenarios. 

<h2 id="conceptual_framework">2. Conceptual Framework</h2>

<span class="tooltip-word">Pull mechanisms<span class="tooltip-text">"Pull incentives" are incentive-based funding that rewards firms after achieving specific results or delivering a successful product. Since funders do not pay upfront, pull mechanisms place risk of technological success on the innovators.</span></span> mimic market incentives by committing to reward innovators of socially valuable goods. At first approximation, when firms evaluate whether to enter a market, they consider whether expected revenues will exceed expected costs. To answer that question, firms need to assess: What is the likelihood of technological success? How much will it cost to pursue innovation? What is the expected market size and timing of future revenue? And how much competition do they expect to face?

The size and structure of the <span class="tooltip-word">pull mechanism<span class="tooltip-text">"Pull incentives" are incentive-based funding that rewards firms after achieving specific results or delivering a successful product. Since funders do not pay upfront, pull mechanisms place risk of technological success on the innovators.</span></span> will dictate the answer to these questions and, hence, determine how many firms try their hand at innovation. Increasing the amount of effort firms put into innovation or increasing the expected number of firms that choose to participate in pull mechanisms increases the probability that at least one attempt yields success. To determine the appropriate reward size, the designer of the <span class="tooltip-word">pull mechanism<span class="tooltip-text">"Pull incentives" are incentive-based funding that rewards firms after achieving specific results or delivering a successful product. Since funders do not pay upfront, pull mechanisms place risk of technological success on the innovators.</span></span>, therefore, needs to consider the tradeoff between increasing the probability that firms succeed at innovation and the cost of the pull mechanism.

<h3 id="firm_decision_making">a. Firm Decision Making</h3>
When designing an innovation incentive, we need a systematic way to think about what motivates firms to participate. Let's start with a simplified view.

Imagine a pharmaceutical company considering whether to develop a new vaccine. They know development will require significant upfront investment in research, clinical trials, and manufacturing capacity. They also know there's a high chance of failure at each stage and that other companies might succeed first.

To decide whether to invest, firms weigh their expected costs against potential rewards. If successful, they'll receive the incentive payment — but they might have to share it with other successful developers. If they fail, they bear all the costs with no return.

Our framework captures this decision-making process. We look at:
<ul>
    <li>the full cost of development, from research through commercialization </li>
    <li>the probability of success at each stage of innovation </li>
    <li>the time value of money between when costs are incurred and payments are received </li>
    <li>the impact of competition on expected returns. </li>
</ul>

 
From the funder’s perspective, the size of the pull mechanism principally depends on the number of firms they want to entice to invest in the target innovation. The following model then maps this desired number of investing firms into a necessary size.

<h3 id="model_setup">b. Model Setup</h3>
To make this analysis tractable, we make some simplifying assumptions:
<ul>
    <li>All firms are rational and risk-neutral: they participate if (and only if) expected revenue exceeds expected costs. </li>
    <li>Firms face one choice: whether to invest in a single innovation attempt.</li>
    <li>All innovation attempts are <span class="tooltip-word">identical<span class="tooltip-text">By identical, we mean that each attempt has the same probability of success, not that they are all pursuing the same method or approach</span></span>,<span class="tooltip-word"> independent<span class="tooltip-text">By independence, we mean that each attempt is uncorrelated with any other attempt, much like how whether a flipped coin comes up heads does not depend on the outcome of the previous flip. We relax this assumption later by allowing different attempts to become correlated with each other</span></span>, and proceed along the same timetable.</li>
    <li>Successful firms share the reward <span class="tooltip-word">equally<span class="tooltip-text">For example, if only one firm succeeds, they receive the entire award. If two firms succeed, they each receive half the reward</span></span>.</li>
    <li>Program benefits do not depend on the number of successful firms. The goal of the funder is for at least one firm to succeed. </li>
</ul>

This model has been deliberated kept simple to make it amenable to working with real-world data. We focus on innovation efforts that progress through discrete stages—like R&D, testing, and approval—because those can be sourced from past projects, expert interviews, or published literature. By structuring the model around commonly observable parameters, we aim to make this a tool that funders can actually apply in practice. More complex dynamics—such as firm heterogeneity, market concentration, or correlated risks—can meaningfully affect outcomes, but are harder to parameterize. We include extensions for these cases in the appendix, where they can be explored as needed for specific applications.

Another modeling choice has been to focus on a particularly simple funding mechanism: a single, lump-sum prize. While this helps clarify the core mechanics of incentive sizing, it may not match every real-world objective. In many cases, it might be more appropriate to allow for multiple winners, offer milestone payments, or design around a different market structure. These variations can significantly affect firm behavior and program cost, and should be considered carefully when adapting the model to a specific context. In later sections (see Appendix B: A Complete Example), we explain how to extend this logic to an advance market commitment with minimal conceptual changes.


*Note: Throughout this post, we use "firm" to refer to any profit-motivated innovator - whether a large company, research institution, startup, or university spinoff.*

<h2 id="understanding_costs">3. Understanding Innovation Costs and Risks</h2>
<h3 id="key_components">a. Key components</h3>
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
    <small>Data from <a href="https://curis.ku.dk/ws/portalfiles/portal/106806762/IFRO_Report_227.pdf">Jensen, J. D., Lund, M., & Fabricius, O. (2014). Economic analysis of developing a Campylobacter vaccine to poultry: a real options approach. Frederiksberg: Department of Food and Resource Economics, University of Copenhagen. <i>IFRO Report, No. 227</i></a></small>.
</p>

<p>
    All-in costs would also need to factor in the cost of building a production facility, marketing, and distribution.
</p>

</div>


**ii. Likelihood of technological success.** Innovation is inherently risky. There is no guarantee that firms that incur R&D and commercialization costs will succeed in developing an innovation and bringing it to market. The probability of success includes a firm's risk of technological failure such that they are unable to fulfill the terms of the technical product parameters. 

Since estimates of success rates vary substantially, designers should be careful that the data source for success rates and costs are consistent. Some sources may estimate a higher success rate because they exclude earlier stages. Or they may estimate the success rate of an entire research program, which includes multiple concurrent attempts, resulting in both a higher success rate but also a higher cost. These alternative approaches are not wrong, but one needs to be careful that the costs and success rates represent the same activities.


<button class="see-more-btn" onclick="toggleDetails('rdsuccess-details')">Continue example</button>
<div id="rdsuccess-details" class="details-box">

Using the same data on chicken vaccine development as before, we can assign probabilities to each step. 
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

</div>

**iii. Firm’s hurdle rate of return.** Firms expect to make a profit and, all else equal, prefer investments that pay money today rather than in the future. Since pull mechanisms require firms to spend money in the present in the hope of future payment, firms will not participate unless adequately compensated for that delay. In general, the more a funder wishes to delay payments (e.g. the technology requires many years to develop and commercialize), the greater the premium the funder must pay to induce entry. MSA currently uses annual discount rates of 8-10%, depending on the sector involved. For long-dated AMCs, i.e. AMCs for technological innovations that may take ten years or more to pay off, including discount rates can more than double nominal costs.

<button class="see-more-btn" onclick="toggleDetails('discountratesizing-details')">How discounting affects AMC sizing (new example)</button>
<div id="discountratesizing-details" class="details-box">



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
            <td>Funder&#39;s needed commitment today if they can invest committed funds with a risk-free 3% annual return</td>
            <td>100</td>
            <td>139</td>
            <td>193</td>
            <td>268</td>
            <td>372</td>
        </tr>
    </tbody>
</table>

Suppose, a firm has a 10% hurdle rate. If the payout is delayed ten years, then the funder will need to pay \$259 in year 10 to induce \$100 in private spending in year 0. 

Formally, if $r$ is the firm hurdle rate and $t$ is the number of years between upfront payment, the nominal value of  the pull commitment to induce \$1 in spending is $$(1+r)^t$$. 

 <div style = "text-align: left;">
    <embed style="border: none;" src="./time_penalty.html" dpi="300" width="105%" height="800px" />
  </div>

</div>

<h3 id="expected_costs">b. Calculating Firms' Expected Costs</h3>

Innovation often requires multiple steps, including research and development, testing, trials, and regulatory approval. Each step incurs its own set of costs and its own risk of failure. However, firms do not incur all costs upfront. Instead, if the project fails at any stage, the firm simply stops and does not incur the costs of subsequent stages. 

When sizing the pull mechanism, we consider the firm's perspective of expected costs at the time of entry, not the total cost of a successful innovation. The expected costs faced by the firm at the time of entry are the cumulative, probability-weighted costs across all development phases, properly discounted for the time value of money. Therefore, the expected cost of an innovation attempt will be less than the total cost of successful innovation.


<button class="see-more-btn" onclick="toggleDetails('optionvalue-details')">See continued example</button>
<div id="optionvalue-details" class="details-box">

Research and development is typically a staged process in which your idea may fail at any given step, allowing one to terminate the process.

Consider the case of the chicken vaccine considered previously. We first need to decompose into annual costs and probabilities of failure so we can calculate expected costs. In cases where a stage takes multiple years, we assume that costs and probabilities of success are equal in all three years (e.g. a three-year, $30 million stage with an overall probability of success of 50% would have annual nominal costs of $10 million and an annual probability of success of 79.4%).

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
            <td>58.4%</td>
            <td>100%</td>
            <td>955 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>649.7</td>
            <td>955</td>
            <td>58.4%</td>
            <td>58.4%</td>
            <td>554 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>649.7</td>
            <td>955</td>
            <td>58.4%</td>
            <td>34.1%</td>
            <td>321 </td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>137</td>
            <td>201</td>
            <td>75%</td>
            <td>19.5%</td>
            <td>39 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>104</td>
            <td>153</td>
            <td>44.7%</td>
            <td>14.6%</td>
            <td>22 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>104</td>
            <td>153</td>
            <td>44.7%</td>
            <td>6.6%</td>
            <td>10 </td>
        </tr>
        <tr>
            <td>Approval</td>
            <td>48</td>
            <td>71</td>
            <td>9%</td>
            <td>3%</td>
            <td>2 </td>
        </tr>
        <tr>
            <td>Release</td>
            <td>-</td>
            <td>-</td>
            <td>100%</td>
            <td>2.7%</td>
            <td>-</td>
        </tr>
    </tbody>
</table>


While the all-in cost of running from start to finish is \$3.4 million, because the innovator stops incurring costs upon failure, the expected cost at time of initiation is only \$1.9 million.


We now need to introduce the time value of money. Discounting reduces future costs, as firms value expenses incurred in the future less than they value expenses they incur in the present. For example, if we use an 8.05% discount rate (from <a href="https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/wacc.html" target="_blank" rel="noopener noreferrer">Damadoran 2024</a>), we get the following table for our livestock vaccine modeling.


  <table>
    <thead>
        <tr>
            <th>Phase</th>
            <th>Cost (2024 1000 $)</th>
            <th>Unconditional Probability of Success</th>
            <th>Probability of reaching step</th>
            <th>Expected Cost (1000 $)</th>
            <th>Discounted Present Value (1000 $)  </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>R&amp;D</td>
            <td>955</td>
            <td>58.4%</td>
            <td>100%</td>
            <td>955</td>
            <td>955 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>955</td>
            <td>58.4%</td>
            <td>58.4%</td>
            <td>554</td>
            <td>513 </td>
        </tr>
        <tr>
            <td>R&amp;D</td>
            <td>955</td>
            <td>58.4%</td>
            <td>34.1%</td>
            <td>321</td>
            <td>275 </td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>201</td>
            <td>75%</td>
            <td>19.5%</td>
            <td>39</td>
            <td>31 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>153</td>
            <td>44.7%</td>
            <td>14.6%</td>
            <td>22</td>
            <td>16 </td>
        </tr>
        <tr>
            <td>Test</td>
            <td>153</td>
            <td>44.7%</td>
            <td>6.6%</td>
            <td>10</td>
            <td>7 </td>
        </tr>
        <tr>
            <td>Approval</td>
            <td>71</td>
            <td>9%</td>
            <td>3%</td>
            <td>2</td>
            <td>1.3 </td>
        </tr>
        <tr>
            <td>Release</td>
            <td>-</td>
            <td>100%</td>
            <td>2.7%</td>
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

Formally, we can say the following: k is the number of innovation steps, and P is a vector representing the probability of advancing from one stage to the next where $P = \{p_0,p_1,p_2, ... , p_k\}$. Let $C$ be a vector representing the cost at each stage $C = \{c_0,c_1,c_2, ... , c_k\}$.

Without consideration of the time value of money, the cost of development is $$\sum_{i=1}^{k} c_i \prod_{j=1}^{i} p_{j-1}$$

</div>

We use the *expected* cost of the innovation attempt to be able to compare to the present value of the *expected* reward from the pull incentive, which is also discounted by time and the probability of success. That is, we are estimating the expected costs and returns from the firm's perspective at the time of entry.

<h3 id="sourcing_parameters">c. Sourcing Parameter Estimates</h3> 
Data on the costs and risks of innovation can be difficult to find, but there are several types of sources we have found useful for gathering this information:
<ul>
    <li><span class="tooltip-word">Academic literature<span class="tooltip-text">One example: <a href="https://curis.ku.dk/ws/portalfiles/portal/106806762/IFRO_Report_227.pdf">DiMasi, Grabowski and Hansen 2016</a></span></span> and industry reports provide historical cost averages </li>
    <li>Government and regulatory filings often contain detailed development costs </li>
    <li>Interviews with industry experts who can validate cost assumptions</li>
    <li>Similar completed projects that provide comparable reference points</li>
</ul>

When using these sources, it is important to be aware of their potential limitations and biases. Published costs often only represent successful attempts. They may also be dated and need adjustment for inflation. Additionally, costs can vary significantly by sector, region, and specific technical challenges. Triangulating between multiple sources can provide a more complete picture. 

Additionally, remember that the goal is to identify the threshold case — the point at which firms are just willing to participate. For simplicity, our model assumes that firms are homogeneous, meaning they share the same cost structure and probability of success. In reality, firms will have a distribution of costs and probabilities, meaning some will find participation attractive at lower incentive levels, while others may require larger incentives. The characteristics we assign to the representative firm in our model should approximate this real-world threshold—capturing the point at which firms on the margin would choose to participate.

<h2 id="program_size">4. Determining the Overall Program Size</h2>

<h3 id="simplest_version">a. Simplest version</h3>

We now have a framework for calculating the expected costs firms face when pursuing innovation. How, then, do we use this to determine the total size of the pull incentive needed?

First, consider perhaps the simplest case: aiming to set an incentive size large enough to motivate one firm to attempt innovation. To accomplish this, the pull incentive needs to provide an expected reward greater than or equal to a firm’s expected cost of an innovation attempt.  In the case of a single firm, the present value of a needed pull incentive is equal to the firm’s expected costs multiplied by the reciprocal of their probability of success. 

For example, for an innovation with a firm’s expected cost of \\$1 million and a 10% chance of success, a pull incentive would need to have a present value of at least \\$10 million. While it may be shocking that \\$10 million is more than an order of magnitude larger firm’s expected costs, remember that pull mechanisms are shifting the risks of development from the funder to the innovator. In this case, rather than the funder spending an expected \\$1 million in up front funding with only a 10% chance of successful innovation, the funder commits to paying \\$10 million only if the innovation is successful. The funder has a 10% chance of paying \\$10 million; in the 90% chance that the innovator is unsuccessful, the funder can repurpose those funds for other projects.

In many cases, the funder may want to create a pull fund that is large enough to incentivize multiple attempts simultaneously in order to have a higher probability of at least one successful innovation. In the next section, we discuss how to choose the target number of attempts.

<h3 id="number_of_attempts">b. Target Number of Attempts</h3>

The key is to recognize that each additional firm attempting innovation increases the overall chances of success. Consider a case where any individual firm has a 10% chance of successfully developing a targeted product. If two firms make an attempt, the overall probability of at least one success increases to 19%, and with three firms, it increases to 27.1%. With multiple firms participating, the chance of at least one success improves. 

At the same time, attracting additional firms becomes increasingly expensive as they have to have to share the reward if several of them succeed. Consider the example where each attempt has an expected cost of \\$1 million and has a 10% chance of success. For a single firm to participate, the reward needs to be at least \\$10 million (to offset the 10% chance of success). For two firms to participate, the reward needs to be higher - about \\$10.5 million - because each firm now faces the risk of having to split the reward if both succeed. For three firms, the required reward increases to about \\$11.1 million. This pattern continues: each additional firm requires a larger incentive to participate than the last because of the increasing risk of having to share the reward.

This creates a fundamental tradeoff: the more firms that participate, the more likely we are to achieve the innovation's benefits—whether that's lives saved by a new vaccine or emissions reduced by green technologies—but increasing this probability becomes increasingly expensive. As a result, setting the right reward size means asking: what is the social value of increasing our chances of achieving these benefits, and how do these compare to the costs? During the COVID-19 pandemic, the massive daily cost of delay meant even small increases in the probability of success had enormous value, justifying efforts to attract many firms ([Ahuja et al 2021](https://www.aeaweb.org/articles?id=10.1257/pandp.20211103)). However, in other cases, the funder may only seek to incentivize a few of the best-suited firms to participate.

<iframe 
    src="needed_attempts_graph.html" 
    width="100%" 
    height="600" 
    style="border: none;">
</iframe>

<button class="see-more-btn" onclick="toggleDetails('needed-attempts-math')">Show math</button>
<div id="needed-attempts-math" class="details-box">
    Recall that we made the following assumptions, many of which will be later relaxed.
    <br>
    <br>
    <ol>
    <li>All firms are rational and risk-neutral: they participate if (and only if) expected revenue exceeds expected cost. </li>
    <li>Firms face one choice: whether to invest in a single innovation attempt. </li>
    <li>All innovation attempts are <span class="tooltip-word">identical<span class="tooltip-text">By identical, we mean that each attempt has the same probability of success, not that they are all pursuing the same method or approach</span></span> and <span class="tooltip-word">independent<span class="tooltip-text">By independence, we mean that each attempt is uncorrelated with any other attempt, much like how whether a flipped coin comes up heads does not depend on the outcome of the previous flip. We relax this assumption later by allowing different attempts to become correlated with each other</span></span> and proceed along the same timetable.</li>
    <li>Successful firms share the reward <span class="tooltip-word">equally<span class="tooltip-text">For example, if only one firm succeeds, they receive the entire award. If two firms succeed, they each receive half the reward</span></span>.</li>
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
    Suppose we want to create a pull mechanism such that the probability that at least one firm succeeds is at least $\theta$. In other words, need to find an $n$ such that $1 - (1-p)^n \geq \theta$. We can rearrange this inequality to express the minimum number of firm entrants needed to reach this probability: 
<!-- -->
    $$ n \geq \frac{\ln(1-\theta)}{\ln(1-p)} $$
<!-- -->
    If the number of entrants $n$ exceeds that value, then the probability of success will exceed that target. As all firms are identical in all respects, the probability of receivng the reward conditional on entering is equal to the probability that any firm succeeds, divided by the number of firms entering. In other words, 
<!-- -->
    $$ \mathbb{P}(win|entry) = \frac{1-(1-p)^n}{n} $$
<!-- -->
    A firm will only enter if its expected revenue exceeds the expected costs ($\mathbb{E}[c]$). For a risk-neutral firm, the expected revenue is simply $\mathbb{P}(win|entry) \cdot X$. As a result, by plugging in the values for $\mathbb{P}(win|entry)$ and $n$ we found above, we find that the required pull size is 
<!-- -->
    $$ X \geq \frac{\ln(1-\theta)}{\theta \cdot \ln(1-p)} \cdot \mathbb{E}[c]$$
 <!-- -->
    Future sections will relax some of these assumptions and build out a complete model.
</div>

<h3 id="cost_of_multiple_attempts">c. The Cost of Incentivizing Multiple Attempts</h3>

The more firms that have already entered, the higher the marginal cost to induce an extra firm, because now firms face higher risk of splitting the prize. As the number of firms increases, the marginal cost to induce a marginal new attempt approaches the expected cost of each additional attempt. For instance, if the probability of success per attempt is 10% and the present value cost of each attempt is \\$100,000 then a funder would need to increase the pull size by \\$66,000 to move from nine to ten attempts. In contrast, moving from 39 to 40 attempts requires an additional marginal cost of \$95,000. The plot below shows the marginal cost of adding additional attempts as a multiple of the expected cost of an individual attempt.

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

    $$\frac{\mathrm{d}X}{\mathrm{d}n} = \mathbb{E}[c] \cdot \frac{1 + (1-p)^n \cdot (n \cdot \ln(1-p) - 1)}{(1-(1-p)^n)^2} $$

    $$ lim_{n \to \infty}(\frac{\mathrm{d}X}{\mathrm{d}n}) = \mathbb{E}[c] $$


</div>

 Now we can calculate the reward size needed in order to induce a given level of firm entry. The following graph shows the pull size if there was no time delay between private investment and receiving payment. In the real world, including the cost of time will increase costs substantially: as we saw in the previous section, the nominal value will be far higher if revenues are delayed substantially. For example, if an <span class="tooltip-word">innovation attempt<span class="tooltip-text">Remember that an “attempt” in this case does not refer to the cost of an entire research program, which can often involve dozens of research attempts. The cost also only refers to the expected cost of a new attempt at the time of initiating, and not the full cost of seeing an attempt all the way through to completion, since most attempts fail well-before incurring the costs of, e.g. late-stage safety & efficacy trials</span></span> costs \\$1 million and each attempt has only a 5% chance of success, then the present value of the incentive needs to be at least \\$66 million to get at least an 80% chance of success. If the payments occurred ten years after the research begins (a realistic timeframe for novel drugs or vaccines) and firms have an 8% discount rate, then the nominal value of the incentive will have to be at least $142 million. 


*Note: The expected cost of an attempt (used when considering firm participation) can be substantially lower than the full actualized development costs. For instance, if full development costs are $20 million but have only a 5% chance of being incurred, the expected cost is \\$1 million, as stated in the example above. This is one of the reasons pull mechanisms appear very large relative to expected costs.*

<button class="see-more-btn" onclick="toggleDetails('push-pull-details')">Some notes on push v. pull</button>
<div id="push-pull-details" class="details-box">
    These large costs seem to beg the question: why not simply pay upfront for innovation (i.e. why not use “push” funding?). After all, paying upfront allows the funder to avoid needing to compensate firms for time delay. This piece is not the venue to get into the complete debate about push versus pull. Suffice to say there are several reasons why pull might be more effective, despite seeming more expensive:
<p></p>
<ol>
    <li> The funder may not be able to identify which firms are the cheapest (i.e. firms have <em> asymmetric information</em>). Since push funding requires the funder to choose firms upfront, push funding may result in rewarding more expensive firms. </li>
    <li> The funder may not be able to identify a specific target product in advance, and thus may prefer a pull approach that is open to multiple different kinds of solutions. </li>
    <li> Push funding does not create incentives for firms to speedily commercialize their products. Many innovations look good on paper but fail to achieve traction in the market; pull funding could save funders money by avoiding payouts for these “false positives.” </li>
</ol>

The complete push v. pull debate deserves far more space than this dropdown can provide. Suffice to say that the need to compensate firms for a lengthy time delay is a reason one might prefer push funding, but other considerations may be decisive in favor of pull depending on the circumstances.

</div>

<iframe 
    src="simple_with_text_box_input.html" 
    width="100%" 
    height="750" 
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
    $$ \text{Pull size present value} \geq \frac{\ln(1 - \theta)}{\theta \cdot \ln(1 - p)} \cdot \mathbb{E}[c] $$
</div>

<h2 id="total_costs">5. Assessing Cost-Effectiveness</h2>

<h3 id="additional_costs">a. Additional Cost Considerations</h3>

Any complete analysis of an innovation incentive program will need to include other necessary costs, beyond those necessary to induce adequate firm entry. In some cases, these additional factors may lower the total necessary cost of the program. These include:

<ul>
    <li><strong>Monitoring and verification.</strong> Pull mechanisms involve paying for success. This requires being able to monitor one’s outcome of interest (e.g. verifying sales, adoption, impact on outcome measures). In some cases, these costs will be significant and should be considered as part of the overall costs of the program in addition to the direct cost of the pull reward. </li>
    <li><strong>Costs of designing and implementing the pull fund.</strong> The institution designing and implementing the pull funding program will incur personnel, administrative, and overhead costs. These are likely to be orders of magnitude smaller than the cost of incentivizing innovation. </li>
    <li><strong>Third-party purchases. </strong> Innovations will differ to the extent to which the funder will need to make up the whole market. For some innovations, there will be significant private demand which can be subtracted from the overall market size to calculate the size of the pull fund needed.  Purchases from other agents are not part of the cost to the funder. However, costs paid by other agents that would be unlikely to occur in the absence of the pull mechanism should be considered when appraising the benefits and costs of the intervention. For example, suppose one needs a \$1 billion market (present value) to create at least a 50% probability that a new diagnostic will be invented but there is only \$600 million in private demand. In this case, the needed pull size will only need to be \$400 million.</li>
</ul>
 

<h3 id="cost_effectiveness">b. Cost Effectiveness</h3>
To determine the overall cost-effectiveness of a pull mechanism, we compare the total costs to the expected benefits of the target innovation.

Pull mechanisms are unique investments in that funders either receive the social return of successful innovation or, should no firm succeed at innovation, the chance to spend their funds on other opportunities at a later date. The money does not disappear if no one succeeds at innovation.

Two useful metrics for considering cost-effectiveness are the benefit-cost ratio and net present value of the project.

The benefit-cost ratio (BCR) indicates the social value generated per dollar spent. It is computed by dividing the expected benefits by the total costs. A BCR greater than 1 signals that the benefits outweigh the costs.


<button class="see-more-btn" onclick="toggleDetails('bcr-details')">Show BCR equation</button>
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

The net present value (NPV) directly quantifies the net societal value created by the pull mechanism, accounting for the time value of money. A positive NPV indicates the intervention generates a net gain for society. To calculate overall net present value teams should multiple the probability of program success by the difference of the present value of benefits and costs

<button class="see-more-btn" onclick="toggleDetails('npv-details')">Show NPV equation</button>
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

<h2 id="conclusion">6. Conclusion</h2>
Determining the right size for a pull mechanism involves carefully balancing multiple factors to create effective innovation incentives while ensuring the efficient use of resources. This guide has laid out a framework for systematically analyzing the key components that drive pull mechanism sizing in the context of pure pull funding programs. The core analysis can be summarized in a series of steps:

**Step 1: Gather Information on Innovation Costs and Risks**
<ul>
    <li>Map out all development stages (R&D, testing, regulatory approval, etc.) </li>
    <li>For each stage, estimate the direct costs, probability of success, and duration</li>
</ul>

**Step 2: Calculate Per-Attempt Expected Cost and Success Probability**
<ul>
    <li>Combine stage-level information to find: </li>
        <ul>
        <li>Expected cost per attempt (accounting for early failures)</li>
        <li>Overall probability of success per attempt</li>
        </ul>
    <li>Apply appropriate discount rate to account for time value of money</li>
</ul>

**Step 3: Determine Program Size**
<ul>
    <li>Start with the base calculation of a pull mechanism to incentivize a single attempt: expected costs divided by the probability of success per attempt </li>
    <li>Determine the desired overall target probability of achieving the innovation by considering:</li>
        <ul>
        <li>The social value of the innovation</li>
        <li>The marginal cost of incentivizing additional attempts</li>
        <li>Available budget constraints</li>
        </ul>
</ul>

**Step 4: Factor in Additional Considerations**
<ul>
    <li>Convert the present value into nominal terms based on the expected payment structure timeline</li>
    <li>Add program costs for:</li>
        <ul>
        <li>Program administration costs</li>
        <li>Monitoring and verification</li>
        </ul>
    <li>Subtract the following from the incentive size:</li>
        <ul>
        <li>Expected private market revenue</li>
        <li>Other funding sources</li>
        </ul>
</ul>

While our framework provides a structured approach to sizing decisions, we've made several simplifying assumptions that practitioners should consider carefully:
<ul>
    <li>We assumed firms are identical. In reality, firms have different capabilities, and a pull mechanism will incentivize the best-suited firms to participate.</li>
    <li>We assumed firms make decisions simultaneously and follow the same development timeline. In practice, firms may make innovation attempts sequentially. This could increase the probability of success of a pull mechanism over a longer timeframe. </li>
    <li>Our base model treats attempts as independent, though the appendix explores the correlation between attempts and multiple attempts made by an individual firm.</li>
    <li>Our model does not capture knowledge spillovers between attempts and firms nor the value of having multiple successful innovations rather than just one. </li>
    </ul>

Additional resources about pull mechanisms are available on the Market Shaping Acceleerator's website. We also welcome practitioners to contact us to discuss specific applications, as each situation requires careful consideration of context-specific factors that may influence optimal incentive design.


<h2 id="appendix">Appendix A: Enriching the Simple Model</h2>

<h3 id="pipeline">a. Within and across firm attempts: pipeline approaches to innovation</h3>

The above analysis assumes a competitive market where each firm makes a single attempt. However, this assumption may be unrealistic, as in reality firms tend to make multiple attempts; why go through all the effort hiring researchers and expensive equipment only to make a single attempt?  Suppose research trials have a 2% success rate and a pull designer desires a 50% probability of at least one success: the above formula suggests that the funder now needs to incentivize at least 35 attempts. The notion that 35 attempts will be satisfied by 35 different firms seems unlikely: maybe five firms conducting seven attempts each is more plausible.

As a result, we can consider how the model changes if one imposes constraints on the number of firms that are <span class="tooltip-word">capable of responding<span class="tooltip-text">In reality, there is no “hard cap” on the number of firms that exist in a market. After all, a large incentive can induce new firms to enter. We impose this limit not as a reflection of reality but rather to tractably illustrate the principle</span></span>. Intuitively, this restriction requires firms to initiate multiple attempts each. The marginal cost to the funder to induce that additional attempt will be higher than under the previous one-attempt-per-firm model as a firm now faces a risk of self-competition. Intuitively, the fewer possible firms in the market, the greater the premium the funder must pay. 

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

The number of attempts needed to achieve at least a $\theta$ probability of success does not change. As a result, we plug $n \geq \frac{\ln(1-\theta)}{\ln(1-p)}$ into the above equation, producing:

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

$$
\mathbb{P}(\text{successes} = i) = \binom{k-1}{i} \cdot \left(p^{\frac{n}{k}}\right)^i \cdot \left((1-p)^{\frac{n}{k}}\right)^{k-1-i}
$$

The above equation is simply an expansion of the binomial formula where the number of attempts per firm is $\frac{n}{k}$ and is equivalent to calculating the probability of any specific number of heads when one flips a weighted coin $k-1$ times when the probability of any given flip resolving as heads if $(1-p)^{\frac{n}{k}}$. In cases where the number of attempts is not divisible by the number of firms, we split proportionately. For example, if there are 27 desired attempts and only five firms, three firms will conduct five attempts each, while two firms will conduct six.

In practice, this approach results in a higher needed pull size than the “one attempt per firm” model, but a lower pull size than the monopolist case. Intuitively, the more attempts per firm, the larger the price premium grows. That said, the result tails off so quickly after the monopolist case that this factor is rarely worth considering. For example, if the probability of success per attempt was 6% and the target probability was 50%, having only four firms results in a pull size 8.8% larger than if there were enough firms to have one attempt per firm, but 25% cheaper than if there were only a single firm. However, if the target probability was 66.67% instead, a four firm world requires a 15.8% premium over the one-firm-per-attempt, but a 59.3% discount from a monopolist situation. 

 <div style = "text-align: left;">
    <embed style="border: none;" src="./number_of_firms_sizing.html" dpi="300" width="100%" height="800px" />
  </div>

</div>

<h3 id="correlation-section">b. Correlated probabilities of success</h3>

The above analysis assumes that all attempts are independent, that is, that different innovation attempts are not related to each other and do not affect each other’s chances of succeeding. This assumption is transparently unrealistic, for two reasons. First, the innovation itself may be impossible (or at least impossible in the near future). No amount of separate attempts would allow ancient Roman scientists to construct a modern computer. This is akin to saying that there is an upper bound on the total probability that at least one attempt succeeds. Second, different attempts all made by the same firm are likely more correlated to each other than they are to attempts made by other firms.

Unfortunately, the level of correlation between attempts is unobservable, and designers should use their discretion to incorporate this factor. In general, considering correlation between attempts will raise costs, generally on the magnitude of 10-50%. 

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

We can thus introduce two sources of correlation: a global parameter that reflects the maximum probability of success given an arbitrarily large number of firms and attempts, and a local parameter that reflects the possibility that any given firm could possibly succeed. These changes effectively add an “impossibility ceiling” on the probability of success.

In practice, introducing this two-stage correlation structure has two effects on the total pull size: 1) the marginal cost of increasing the target probability of success rises dramatically and 2) the marginal cost for having a concentrated market with few firms rises concurrently. 

In the following equations, let  represent the global possibility parameter and  be the intra-firm possibility parameter. m is the number of attempts per firm.

Set aside the global parameter for now and let us focus our efforts on the within-firm possibility parameter $\gamma$. 

$$\mathbb{P}_{firm}(success \geq 1) = \gamma \cdot (1-(1-p)^m) $$

The probability that all of a firm's attempts fail is the sum of the probability that the approach is fundamentally infeasible ($1 - \gamma$) and the probability that the approach is feasible ($\gamma$) but all of the attempts fail regardless ($(1-p)^m$). Putting together, one gets $$\mathbb{P}_{firm}(success \geq 1) = 1 - [(1-\gamma) + \gamma \cdot (1-p)^m]$$

This equation simplifies to the previous equation. Now to introduce the global possibility parameter $\eta$.

$$\mathbb{P}_{all}(success \geq 1) = \eta \cdot (1 - [1-\gamma \cdot (1-(1-p)^m)]^k) \geq \theta$$

The goal is to get the probability of success to exceed the target threshold. With the new global possibility parameter, the probability that at least one firm succeeds is the probability that any given firm succeeds conditional on the innovation being possible (from Equation 4.1) multiplied by the possibility $\eta$ that the innovation is at all possible.

$$m \geq \frac{\ln(1-\frac{1-(1-\frac{\theta}{\eta})^{\frac{1}{k}}}{\gamma})}{\ln(1-p)}$$

Algebraic rearrangement of the second equation produces the third. There is no simplified form for the necessary pull size. Instead, one can insert the value of $m$ into the equation for the finite firms, replacing the $\frac{n}{k}$ term that represnts attempts per firm with the value for $m$ found in Equation 4.3.

</div>

In practice, introducing correlation substantially increases the needed pull size, as the number of attempts needed to reach the same probability of success increases dramatically. 


<h3 id="subsidy-passthrough-section">c. Subsidy passthrough</h3>

Our existing method estimating the appropriate size of an advance market commitment (AMC) assumes that the innovative firm receives the entirety of the subsidy pool, with no effect on the price of the novel good sold. For example, this model assumes that a three dollar per-unit subsidy would increase the profit per good sold by precisely three dollars.

This assumption is transparently erroneous. Absent binding supply constraints, increasing the profitability per good sold will induce firms to produce more. Assuming a downward-sloping demand curve, greater supply will in turn induce lower prices. By driving prices lower, the firm captures only part of the subsidy, while consumers capture the rest. A three dollar per-unit subsidy will not increase profit per good sold by three dollars, but instead some unknown value less than three dollars. We consider the transmission of the subsidy to the consumer the problem of subsidy passthrough.

In the existing model, doubling the number of firms cuts the profit per fim in half. A monopolist gets 100% of the total pool of money, a duopolist gets 50%, a triopolist 33.3%, etc. But, as above, this assumption is inaccurate for two reasons. First, competition induces firms to pass some of the subsidy onto the consumer, so a duopolist should get less than 50% of the profit of a monopolist. Second, competition induces firms to expand supply, by weakening the incentive for strategic withholding, which may increase total profits.

Let us start by assuming Cournot competition, where firms decide the amount of quantity to produce and then the market sets the price. This model of competition hews more closely to reality for manufactured goods where capacity (e.g. the size of the factory) must be installed ahead of time; firms cannot costlessly and instantaneously ramp up their supply. The precise number depends on the exact slope of the supply and demand curve, but in general, the Cournot model produces a roughly 55% reduction in profit when moving from one to two firms. More generally, each of the k-firms will receive $\frac{4}{(k+1)^2}$ of the profit of a monopolist, instead of $\frac{1}{k}$.

<button class="see-more-btn" onclick="toggleDetails('subsidy-passthrough')">Show math</button>
<div id="subsidy-passthrough" class="details-box">

<p>Assume a linear demand curve of the form $P(q) = a - b \cdot q$  where $P$ represents price, $a$ and $b$ are constants, and $q$ is the quantity set. The cost of production is constant at $c$ and the subsidy is $s$.</p>

<p>Profit $\pi$ for a monopolist is set by the formula $\pi = (p - c + s) \cdot q$</p>

<p>We can plug in the formula for p we found above and get $\pi = (a - b \cdot q - c + s) \cdot q$</p>

<p>This expands out to $\pi = a \cdot q - b \cdot q^2 - c \cdot q + s \cdot q$ </p>

<p>To maximize profit, we take the derivative of profit with respect to quantity, which is $\frac{d\pi}{dq} = a - 2 \cdot b \cdot q  - c + s$, and set equal to 0.</p>

<p>In the end, we get $q = \frac{a - c + s}{2b}$</p>

<p>Plug that value of $q$ into our formula for profit and we get $\pi = \frac{(a-c+s)^2}{4 \cdot b}$ </p>

<p>How about for a duopolist? Much of the set up is the same, except that $q = q_1 + q_2$ and the firm can only control $q_1$. So we have $\pi_1 = (a - b \cdot (q_1 + q_2) - c + 2) \cdot q_1$ </p>

<p>Because only $q_1$ is under our control, we take the derivative of $\pi$ with respect to $q_1$ and get $\frac{d\pi}{dq_1} = a -2 \cdot b \cdot q_1 - b \cdot q_2 - c + s = 0 $</p>

<p>Since both firms are identical, we can now say $q_1 = q_2$. We can thus solve for $q_1 = \frac{a - c + 2}{3 \cdot b}$. Note that this results in a per-firm quantity $\frac{2}{3}$ of the monopolist quantity (and a total quantity that's $\frac{4}{3}$ as large).</p>

<p>Plugging into the formula for profit, we get $\pi_q = \frac{(a-c+s)^2}{9 \cdot b}$. We can thus see that the profit is $\frac{4}{9}$ as large with the duopolist as with the monopolist firm.</p>

<p>Extending to k-firms follows the same method. We just have $q = q_1 + q_2 + \ldots + q_k$ and $\pi_1 = (a - b \cdot (q_1 + q_2 + \ldots + q_k) - c + s) \cdot q_1$. One can still take the derivative $\frac{d\pi}{dq_1} = a - 2 \cdot b \cdot q_1 - b \cdot q_2 - \ldots - b \cdot q_k - c + s = 0$. Since $q_1 = q_2 = \ldots = q_k$, we can see that a k-opolist receives $\frac{(a-c+s)^2}{(k+1)^2}$. The ratio of profit for a k-opolist to a monopolist is thus just $\frac{4}{(k+1)^2}$. A duopoist receives 44% of the profit, a triopolist receives 25%, etc.</p>

<p>This result is not unique to linear demand functions. "Normal-looking" exponential or logarithmic demand functions that are standard in the literature all will produce very similar results. The sole exception will be "unusual" looking demand curves (e.g. perfectly elastic or inelastic demand, or step-wise functions, etc.)</p>

<p>Installing a 10-20% premium on top of the existing model would be an over-simplification, though not a terribly inaccurate one. A small AMC where the probability of multiple successful winners is very low will need little premium. A large AMC where one targets a high probability of success (and thus a high probability of duplication) will need a larger premium. In the chart below, the y-axis represents the increase in relative payments incorporating passthrough to the previous estimates, which assumed 0% passthrough.</p>

<div style = "text-align: left;">
    <embed style="border: none;" src="./passthrough_chart.html" dpi="300" width="90%" height="900px" />
  </div>


</div>





<h2 id="complete_example">Appendix B: A Full Example</h2>

The following button will walk the reader through a complete example from start to finish, using the case study of vaccines to reduce enteric methane emissions from cattle that the MSA has worked on over the last year.

<button class="see-more-btn" onclick="toggleDetails('complete-example-details')">Show complete example</button>
<div id="complete-example-details" class="details-box">

<strong>Step 1 and 2 - Expected Costs and Risks</strong>

<p>
In previous examples, we used this table from <a href="https://curis.ku.dk/ws/portalfiles/portal/106806762/IFRO_Report_227.pdf">Jensen 2014</a>  to find the expected cost and risk per innovation attempt. Even though the all-in cost of seeing an attempt through from initiation to success is \$3.4 million, because the supermajority of attempts fail far before the test and approval phases, the expected cost at time of initiation is only \$1.904 million. After discounting using an 8.05% discount rate (to recognize the fact that costs borne in future years count “less” than costs incurred in the present, the “expected cost per attempt” becomes \$1,799,000 with a probability of success of 2.7%.
</p>

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
            <td><strong>Overall</strong></td>
            <td><strong>3,443</strong></td>
            <td>-</td>
            <td><strong>2.70%</strong></td>
            <td><strong>1,904</strong></td>
            <td><strong>1,799</strong></td>
        </tr>
    </tbody>
</table>

<strong>Step 3 - Calculating Needed Pull Size</strong>

<p>
$$ X \geq \frac{\ln(1-\theta)}{\theta \cdot \ln(1-p)} \cdot \mathbb{E}[c]$$

We can now plug in these numbers to our formulas shown above, using \$1,799,000 as $\mathbb{E}[c]$ and 0.027 as $p$. The target probability of success $\theta$ is a choice of art, and the following chart shows the needed pull size depending on the choice of the target probability of success.

</p>

<div style = "text-align: center;">
    <embed style="border: none;" src="./example_sizing.html" dpi="300" width="90%" height="550px" />
  </div>

<strong>Step 4 - Adding in Complications</strong>
<p>

$$ V(X,k) \cdot p \cdot (1-p)^{\frac{n}{k} - 1} \geq \mathbb{E}[c]$$

$$\mathbb{V}(X, k) = \sum_{i=0}^{k-1} \frac{1}{i+1} \cdot \mathbb{P}(\text{successes} = i) \cdot X $$

$$
\mathbb{P}(\text{successes} = i) = \binom{k-1}{i} \cdot \left(p^{\frac{n}{k}}\right)^i \cdot \left((1-p)^{\frac{n}{k}}\right)^{k-1-i}
$$

$$m \geq \frac{\ln(1-\frac{1-(1-\frac{\theta}{\eta})^{\frac{1}{k}}}{\gamma})}{\ln(1-p)}$$

If one wishes, one can now add in some of the complications from before, such as reasonable guesses about the number of participating firms and the extent to which this innovation is even “possible”. Both of these terms are highly subjective, and should be informed by interviews with industry experts. For this example, let us assume there are at most six firms in the market, with a global possibility parameter of 75% ($\eta$) and a within-firm possibility parameter of 66.67% ($\gamma$) (in other words, there exists only a three-quarters chance that this innovation is possible and, conditional on the innovation being possible, there is only a two-thirds chance that any given pathway to achieve that innovation could work). 
</p>

<em>Note: As a side note, when one adds in these correlations, we do need to adjust the value of the probability of success $p$ conditional on the innovation being possible. If our data says (e.g.) that these trials succeed 2.7% of the time, then the probability that the trials succeed conditional on being possible at all (using our parameters) becomes </em> $0.027 \div \frac{3}{4} \div \frac{2}{3} = 0.054 = 5.4\%$

<p></p>
<strong>Converting into Nominal Terms</strong>

<p>
The above formula gives only the present value to the firm. But it does not tell us exactly how much money one needs to raise. To do so, we need to understand how long this innovation might take. More distant innovations will result in longer lags between research investment and ultimate payout, and thus require larger rewards in order to induce entry. Industry literature and expert interviews can give some bounds on this estimate. In this case, let us assume that research takes eight years from start to finish.
</p>

<p>
The structure of the pull incentive affects the next step. In the case of a prize, once the research target has been achieved, the firm can receive all of the reward. In the case of an advance market commitment (AMC), the payments are structured as per-unit subsidies. For this example, let us assume the incentive is an AMC that lasts for ten years and payments occur contemporaneously with sales. 
</p>

<p>
In this case, we would need to have a rough model of rollout, which can be informed by the rollout of other products in the space. This payment structure will further increase costs, because sales growth tends to take time, which further increases the wedge between initial investment and ultimate payout. 
</p>

<div style = "text-align: center;">
    <embed style="border: none;" src="./vaccine_rollout.html" dpi="300" width="90%" height="500px" />
  </div>

<p>
At this step, one also needs to include marginal costs of production and add those to the needed subsidy, while subtracting out any private willingness-to-pay. In the case of our methane-reducing vaccines, both the cost of production and private willingness-to-pay might be extremely low (e.g. \$2.25/dose and \$0, respectively). 
</p>

<p>
Consider the above logistic chart of potential rollout. Cognizant that sales made in later years are less valuable to the company in present-value terms than sales made earlier, we can use computers to find the value of a per-unit subsidy such that the present value of all of these future payments exceeds \$227.8 million. To do so, one takes the number of doses projected to be sold each year and discount them (using the firm’s 8.05% discount rate) into “effective number of doses in current-year terms”. 
</p>

<table border="1" cellspacing="0" cellpadding="5">
  <thead>
    <tr>
      <th>Year</th>
      <th>Projected Vaccinations (millions)</th>
      <th>Discount Factor</th>
      <th>Effective Present Vaccinations (millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0-8</td>
      <td>0</td>
      <td>0.538</td>
      <td>0</td>
    </tr>
    <tr>
      <td>9</td>
      <td>0.302</td>
      <td>0.498</td>
      <td>0.15</td>
    </tr>
    <tr>
      <td>10</td>
      <td>0.797</td>
      <td>0.461</td>
      <td>0.367</td>
    </tr>
    <tr>
      <td>11</td>
      <td>2</td>
      <td>0.427</td>
      <td>0.854</td>
    </tr>
    <tr>
      <td>12</td>
      <td>4.518</td>
      <td>0.395</td>
      <td>1.785</td>
    </tr>
    <tr>
      <td>13</td>
      <td>8.4</td>
      <td>0.365</td>
      <td>3.066</td>
    </tr>
    <tr>
      <td>14</td>
      <td>12.28</td>
      <td>0.338</td>
      <td>4.15</td>
    </tr>
    <tr>
      <td>15</td>
      <td>14.8</td>
      <td>0.313</td>
      <td>4.63</td>
    </tr>
    <tr>
      <td>16</td>
      <td>16</td>
      <td>0.29</td>
      <td>4.64</td>
    </tr>
    <tr>
      <td>17</td>
      <td>16.5</td>
      <td>0.268</td>
      <td>4.422</td>
    </tr>
    <tr>
      <td>18</td>
      <td>16.69</td>
      <td>0.248</td>
      <td>4.139</td>
    </tr>
    <tr>
      <td><strong>Total</strong></td>
      <td><strong>92.287</strong></td>
      <td></td>
      <td><strong>28.203</strong></td>
    </tr>
  </tbody>
</table>


<p>
Then divide the total needed present value (\$227.8 million) by the “effective present value of doses” and add in the \$2.25 to offset the cost of production to get a final answer of \$10.33/dose. We now have a total nominal price tag of \$952.4 million (multiplying the total subsidized doses by the total nominal cost). If we assume that the funder can earn a risk-free 2% interest rate on the money they put in escrow, the total amount of money they need to commit becomes <strong>\$702.1 million</strong>. Why is this value so much greater than the original \$227.8 million we found? Because the time value of money to the firm (8.05%) far exceeds the interest that the funder can get on the money they put in escrow (2%).
</p>

</div>

<iframe 
    src="complete_sizing_graph.html" 
    width="100%" 
    height="900" 
    style="border: none;">
</iframe>

--------
With thanks to Chris Snyder, Siddhartha Haria, Sebastian Quaade, Leah Rosenzweig, Rebecca Rolapp, Jano Costard, Elisabeth Hofmeister, and Sarah Daniels for feedback.  


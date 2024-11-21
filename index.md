---
layout: default
title: How to Size an AMC
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



<h2>Introduction</h2>

Pull funding mechanisms, such as prizes and advanced market commitments, can be powerful tools to incentivize the development and delivery of socially valuable innovations. They provide financial incentives to innovators, helping to bridge gaps in markets where public health or social benefits might otherwise be underfunded. However, a key challenge in designing effective pull funding is determining the appropriate size of the incentive.

Over the past year, we have developed an evolving framework to determine the approximate size of a pull fund for our target innovations. We have used this approach to estimate the cost-effectiveness and investigate the impact of design choices.

In this blog, we will present a simple framework for determining the size of pull funding for others interested in using these mechanisms. We simplify assumptions of market structure and competitive dynamics to have a generalized approach that can be applied to a wide variety of projects. The specifics of any market will add complexity that extends beyond this baseline framework. For additional considerations, refer to Section 5. 


<h2>Size of the incentive</h2>

Pull mechanisms mimic market incentives by committing to provide sufficient returns to innovators of socially valuable goods. When firms evaluate participation in a pull mechanism, they consider whether expected revenues exceed expected costs. We expect firms to weigh the crucial questions of any innovation investments: what is the likelihood of technological success? How much will it cost to pursue it? What is the expected market size and timing of future revenue? How much competition do they expect to face?

The design and size of the pull mechanism will dictate the answer to these questions and, hence, determine how many firms choose to invest in attempts at innovation. Increasing the expected number of firms that choose to participate in pull mechanisms increases the probability that the whole endeavor yields success. To determine the appropriate size of a pull mechanism, a designer needs to consider the tradeoff between increasing the probability of success and the cost of the endeavor. 
 
The remainder of this section will explain how to estimate the costs and risks of development and how to size a pull mechanism that achieves a desired probability of success. 

<h2>Estimating Firms' Costs</h2>
First, we need to understand the costs that firms face. The higher the cost of innovation, the larger the pull size needs to be. Examples of costs worth considering include:

**i. Cost of R&D and commercialization.** This includes the fixed and marginal costs to a firm to invent, produce, and deliver the desired product. For some problems, the main challenge is to incentivize firms to incur fixed costs on research and development. In other cases, there may also be significant costs in bringing it to market at an appropriate scale. This could also include costs associated with demonstrating success and overcoming regulatory hurdles. 

<button class="see-more-btn" onclick="toggleDetails('rdcosts-details')">Show example</button>
<div id="rdcosts-details" class="details-box">
    <p>
    For example, consider an AMC to incentivize the development of a livestock vaccine. We can use past data on crop innovations to inform our estimates on the cost of development. The following comes from a 2014 paper estimating the costs to develop a vaccine for chicken in 2009. Any forward-looking estimates would need to adjust for inflation.
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
            <td>R&D</td>
            <td>3</td>
            <td>1,949</td>
        </tr>
        <tr>
            <td>Patent</td>
            <td>1</td>
            <td>137</td>
        </tr>
        <tr>
            <td>Test</td>
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


**ii. Likelihood of technological success.** Innovation is inherently risky. There is no guarantee that firms that incur R&D and commercialization costs will succeed in developing an innovation and bringing it to market. The probability of success includes a firm's risk of technological failure such that they are unable to reach TPP. 

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
            <td>R&amp;D</td>
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

**iii. Firm’s hurdle rate of return.** Firms expect to make a profit, and prefer investments that pay money today rather than in the future. Since AMCs and other pull mechanisms require firms to spend money in the present on the possibility of receiving funds in the future, funders need to compensate firms for that delay. In general, the more a funder wishes to delay funding, the greater the premium the funder must pay to induce entry. MSA currently uses annual discount rates of 8-10%, depending on the sector involved. For long-dated AMCs, i.e. AMCs for technological innovations that may take ten years or more to pay off, including hurdle rates can more than double nominal costs.

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
    <embed style="border: none;" src="./time_penalty.html" dpi="300" width="100%" height="800px" />
  </div>

</div>

<h2>Calculating Firms' Expected Costs</h2>

Innovation requires multiple steps, including research and development, testing, trials, and regulatory approval. Each step incurs its own set of costs. However, when sizing, it is important to remember that firms do not incur these costs all at once. Instead, if the project fails at any specific step, the firm simply stops and does not incur the costs of the subsequent stages. Instead, when sizing, one needs to calculate the expected cost at the time of entry, properly discounted by time.


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

# Building the model

Larger market sizes will incentivize more firms to participate. Designers should consider the number of firms they are seeking to attract and the eternal tradeoff: a larger AMC creates more chances for a successful innovation but also entails higher costs. For example, during the COVID-19 pandemic, it was important to attract firms with even a modest probability of success which contrasts from the classic case for an advance market commitment ([Ahuja et al 2021](https://www.aeaweb.org/articles?id=10.1257/pandp.20211103)). However, normally we do not want to attract a lot of firms who have a low probability of success — one of the benefits of pull is that firms with a high probability of success self-select into the R&D. Thinking through how many firms are likely to be attracted to compete for the pull mechanism or we want to see compete is a key ingredient in the costing analysis.

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





<h2>Other considerations</h2>

<h3>Within and across firm attempts: pipeline approaches to innovation</h3>

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

<h3>Correlated probabilities of success</h3>

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

---

William Arnesen & Claire Mcmahon, 2024

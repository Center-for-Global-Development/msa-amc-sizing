---
layout: default
title: How to Size an AMC
---

<style>
    .details-box {
        display: none; /* Hide by default */
        margin: 10px 0;
        padding: 10px;
        border: 1px solid #ddd;
        background-color: #f9f9f9;
    }

    .see-more-btn {
        display: inline-block;
        margin-top: 10px;
        padding: 10px 15px;
        font-size: 1em;
        background-color: #007BFF;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }

    .see-more-btn:hover {
        background-color: #0056b3;
    }
</style>

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



# Introduction

Pull funding mechanisms, such as prizes and advanced market commitments, can be powerful tools to incentivize the development and delivery of socially valuable innovations. They provide financial incentives to innovators, helping to bridge gaps in markets where public health or social benefits might otherwise be underfunded. However, a key challenge in designing effective pull funding is determining the appropriate size of the incentive.

Over the past year, we have developed an evolving framework to determine the approximate size of a pull fund for our target innovations. We have used this approach to estimate the cost-effectiveness and investigate the impact of design choices.

In this blog, we will present a simple framework for determining the size of pull funding for others interested in using these mechanisms. We simplify assumptions of market structure and competitive dynamics to have a generalized approach that can be applied to a wide variety of projects. The specifics of any market will add complexity that extends beyond this baseline framework. For additional considerations, refer to Section 5. 


## Size of the incentive

Pull mechanisms mimic market incentives by committing to provide sufficient returns to innovators of socially valuable goods. When firms evaluate participation in a pull mechanism, they consider whether expected revenues exceed expected costs. We expect firms to weigh the crucial questions of any innovation investments: what is the likelihood of technological success? How much will it cost to pursue it? What is the expected market size and timing of future revenue? How much competition do they expect to face?

The design and size of the pull mechanism will dictate the answer to these questions and, hence, determine how many firms choose to invest in attempts at innovation. Increasing the expected number of firms that choose to participate in pull mechanisms increases the probability that the whole endeavor yields success. To determine the appropriate size of a pull mechanism, a designer needs to consider the tradeoff between increasing the probability of success and the cost of the endeavor. 
 
The remainder of this section will explain how to estimate the costs and risks of development and how to size a pull mechanism that achieves a desired probability of success. 

## Estimating Firms' Costs 
First, we need to understand the costs that firms face. The higher the cost of innovation, the larger the pull size needs to be. Examples of costs worth considering include:

**i. Cost of R&D and commercialization.** This includes the fixed and marginal costs to a firm to invent, produce, and deliver the desired product. For some problems, the main challenge is to incentivize firms to incur fixed costs on research and development. In other cases, there may also be significant costs in bringing it to market at an appropriate scale. This could also include costs associated with demonstrating success and overcoming regulatory hurdles. 

<button class="see-more-btn" onclick="toggleDetails('simple-details')">See more details</button>
<div id="rdcosts-details" class="details-box">
    <p>
    For example, consider an AMC to incentivize the development of a livestock vaccine. We can use past data on crop innovations to inform our estimates on the cost of development. The following comes from a 2014 paper estimating the costs to develop a vaccine for chicken in 2009. Any forward-looking estimates would need to adjust for inflation.
</p>

<table style="width: 100%; border-collapse: collapse; margin: 20px 0; text-align: left;">
    <thead>
        <tr style="background-color: #f2f2f2;">
            <th style="border: 1px solid #ddd; padding: 8px;">Phase</th>
            <th style="border: 1px solid #ddd; padding: 8px;">Duration (Years)</th>
            <th style="border: 1px solid #ddd; padding: 8px;">Reported Cost (1000 €)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="border: 1px solid #ddd; padding: 8px;">R&D</td>
            <td style="border: 1px solid #ddd; padding: 8px;">3</td>
            <td style="border: 1px solid #ddd; padding: 8px;">1,949</td>
        </tr>
        <tr>
            <td style="border: 1px solid #ddd; padding: 8px;">Patent</td>
            <td style="border: 1px solid #ddd; padding: 8px;">1</td>
            <td style="border: 1px solid #ddd; padding: 8px;">137</td>
        </tr>
        <tr>
            <td style="border: 1px solid #ddd; padding: 8px;">Test</td>
            <td style="border: 1px solid #ddd; padding: 8px;">2</td>
            <td style="border: 1px solid #ddd; padding: 8px;">208</td>
        </tr>
        <tr>
            <td style="border: 1px solid #ddd; padding: 8px;">Approval</td>
            <td style="border: 1px solid #ddd; padding: 8px;">1</td>
            <td style="border: 1px solid #ddd; padding: 8px;">48</td>
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

**iii. Firm’s hurdle rate of return.** Firms expect to make a profit, and prefer investments that pay money today rather than in the future. Since AMCs and other pull mechanisms require firms to spend money in the present on the possibility of receiving funds in the future, funders need to compensate firms for that delay. In general, the more a funder wishes to delay funding, the greater the premium the funder must pay to induce entry. MSA currently uses annual discount rates of 8-10%, depending on the sector involved. For long-dated AMCs, i.e. AMCs for technological innovations that may take ten years or more to pay off, including hurdle rates can more than double nominal costs.





## Explore the Simple Sizing Graph

<iframe 
    src="simple_sizing_graph.html" 
    width="100%" 
    height="650" 
    style="border: none;">
</iframe>

<button class="see-more-btn" onclick="toggleDetails('simple-details')">See more details</button>
<div id="simple-details" class="details-box">
    The Simple Sizing Graph is based on the following equation:
    <p>
        \( \text{Cost} = \frac{\ln(1 - \theta)}{\theta \cdot \ln(1 - p)} \)
    </p>
    This equation captures the relationship between the target probability of success (\( \theta \)) and the required cost as a multiple of the innovation cost.
</div>

## Needed Firm Entry Graph

<iframe 
    src="needed_attempts_graph.html" 
    width="100%" 
    height="650" 
    style="border: none;">
</iframe>

## Complete Sizing Graph

<iframe 
    src="complete_sizing_graph.html" 
    width="100%" 
    height="800" 
    style="border: none;">
</iframe>

---

© 2024 William Arnesen & Claire Mcmahon

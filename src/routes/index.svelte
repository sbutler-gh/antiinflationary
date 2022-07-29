<script>
        import Chart from 'svelte-frappe-charts';

        let bike_rebate_data = {
        labels: ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10"],
        datasets: [
          {
            values: ["0", "7000", "14000", "21000", "28000", "35000", "42000", "49000", "56000", "63000", "70000"],
            // values: [...Array((Math.ceil(payback_years)+4)).keys()].map(multiplySavingsKept),
            chartType: 'line',
            lineOptions: { regionFill: 1}
          },
          {
            values: ["2000"],
          },
          // {
          //   values: [cost_per_user],
          // }
        ],
        // yRegions: [{ label: "Region", start: 100, end: 4000 }],
        // yMarkers: [
        //       {
        //           label: "Project Cost",
        //           value: cost_per_user,
        //           options: { labelPos: 'left' } // default: 'right'
        //       }
        //   ]
      };

      let cepp_data = {
        labels: ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10"],
        datasets: [
          {
            values: ["0", "24", "48", "72", "96", "120", "144", "168", "192", "216", "240"],
            // values: [...Array((Math.ceil(payback_years)+4)).keys()].map(multiplySavingsKept),
            chartType: 'line',
            lineOptions: { regionFill: 1}
          },
          {
            values: ["150"],
          },
          // {
          //   values: [cost_per_user],
          // }
        ],
        // yRegions: [{ label: "Region", start: 100, end: 4000 }],
        // yMarkers: [
        //       {
        //           label: "Project Cost",
        //           value: cost_per_user,
        //           options: { labelPos: 'left' } // default: 'right'
        //       }
        //   ]
      };

      let lineOptions =  {
          regionFill: 1 // default: 0
          }

      let ebike_investment = 1;
      let ebike_investment_unit = 1000000000;
      let cepp_investment = 150;
      let cepp_investment_unit = 1000000000;
</script>

<div style="text-align: center;">
<h1>Anti-inflationary US</h1>
<p>The best policies for reversing inflation, balancing the federal books, and saving Americans money.</p>
</div>

<section class="policies">
<div class="policy">
  <h2>E-bike and bike rebates</h2>
  <p>Rebates towards the purchase of e-bikes, bicycles, and e-cargo bikes, which can be redeemed <strong>at time of purchase.</strong>  (If it's a deduction on end-of-year taxes, people will be less likely to use the rebate, which limits the anti-inflationary benefits.)</p>
  <h3>For every <span class="invested">$1 invested</span>, e-bike and bike rebates return <span class="returns">$150 in savings</span> over a ten-year period (for federal, state, and local governments, and for commuters).</h3>
  <p>Investing $<input type="number" style="width: 40px" bind:value={ebike_investment}> <select bind:value={ebike_investment_unit}><option value={1000000}>million</option><option value={1000000000} selected>billion</option></select> into e-bike and bike rebates, generates <span class="green">${(ebike_investment * 150 * ebike_investment_unit).toLocaleString()} in savings</span>.</p>
  <Chart data={bike_rebate_data} type="line" lineOptions={lineOptions} colors={['green', 'red']}/>
  <p>⚡ For the same amount of batteries that go in a single electric truck sold for $70,000, we could produce +250 electric bikes sold for $1,000,000.</p>
  <p>Sources of data:</p>
  <ul>
    <li>The average cost of owning a car is <a href="https://www.nerdwallet.com/article/loans/auto-loans/total-cost-owning-car">$9,666 per year</a>, including car payments, insurance, gas, gas taxes, parking, maintenance, and other costs. (https://www.nerdwallet.com/article/loans/auto-loans/total-cost-owning-car)
      <ul>
        <li>Across 130 million commuters in the USA, that costs us $1,300,000,000,000 per year.</li>
      </ul>
    </li>
    <li>Across the US, state and local governments pay $617 per capita on highways and roads every year.
      <ul>
        <li>With 329 million people in the United States, that costs us $203 billion every year.</li>
      </ul>
    </li>
    <li>The total we pay for parking in the United States amounts to $2,300 per vehicle. (https://usa.streetsblog.org/2017/07/26/if-americans-paid-for-the-parking-we-consume-wed-drive-500-billion-fewer-miles-each-year/)
      <ul>
        <li>With 230 million vehicle in the US, we pay approximately $529 billion every year on parking spaces.</li>
      </ul>
    </li>
    <li>Adding these figures together, we spend approximately $2 trillion per year on car infrastructure, including the costs of car ownership, the costs of road and highway spending, and the costs of parking spaces and the real estate they occupy.
      <ul>
        <li>With 130 million commuters in the US, we can save $15000 every year by transitioning from car infrastructure to bike infrastructure.</li>
      </ul>
    </li>
    <li>If an e-bike rebate costs $2000 per commuter, which would cover the full cost of an e-bike for many models and up to 50% of the cost for cargo bikes, that would save $15000 for each commuter who switches from a car to a bike.
      <ul>
        <li>Over a ten-year period, that is approxiamately $150,000 in savings for each commuter who switches from a car to a bike.</li>
      </ul>
    </li>
    <!-- <li>The cost of outdoor parking is X.  The cost of indoor parking is X.  The cost of underground parking is X.  The real estate lost for each parking space is X.
      <ul>
        <li>Across the USA, new car parking costs X per year, and existing parking loses X in real estate per year.</li>
      </ul>
    </li> -->
    <li>The F-150 Lightning battery weights 1,800 pounds. (https://fordauthority.com/2021/05/2022-ford-f-150-lightning-battery-reportedly-weighs-1800-pounds/).  The average e-bike battery weighs 7 pounds. (https://www.sixthreezero.com/blogs/bike-advice/how-much-does-an-electric-battery-weigh-or-how-heavy-are-e-bike-batteries)
      <!-- <ul>
        <li>Across the USA, new car parking costs X per year, and existing parking loses X in real estate per year.</li>
      </ul> -->
    </li>
  </ul>
</div>
<br>
<div class="policy">
  <h2>Clean Electricity Performance Plan</h2>
  <p>Give money to utilities who increase renewable energy capacity, and fine utilities who fail to do so.</p>
  <h3>For every <span class="invested">$1 invested</span>, the clean electricity performance plan returns <span class="returns">$2.4 in savings</span>.</h3>
  <h3>For every <span class="invested">$1 invested</span>, the clean electricity performance plan generates <span class="returns">$6 of economic value</span>.</h3>
  <p>Investing $<input type="number" style="width: 40px" bind:value={cepp_investment}>
    <select bind:value={cepp_investment_unit}><option value={1000000000} selected disabled>billion</option></select> into a Clean Electricity Performance Plan generates <span class="returns">${(cepp_investment * 2.4 * cepp_investment_unit).toLocaleString()} in savings</span>.</p>
  <p>⚡ The CEPP is the best way to rapidly reduce emissions reductions, in line with our IPCC goals for 2030.</p>
  <Chart data={cepp_data} type="line" lineOptions={lineOptions} colors={['green', 'red']}/>
  <p>Sources of data:</p>
  <ul>
    <li>The $150B clean electricity performance plan would inject $907 billion into the U.S. economy and raise $154 billion in tax revenue for federal, state, and local governments.(https://www.nrdc.org/media/2021/210909)
      <!-- <ul>
        <li>For X drivers in the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li>$150 billion in CEPP investments could reduce Americans’ electricity bills by 5%, compared to the same power sector transformation without federal grants. (https://www.evergreenaction.com/blog/the-clean-electricity-performance-program-is-key-to-delivering-on-climate)
      <!-- <ul>
        <li>For X drivers in the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li>With Americans expected to pay $556 billion in electricity costs in 2022, a 5% reduction means $27,807,000,000 in savings per year.  That is $278 billion in savings over a ten-year period, for a policy that costs $150 billion.
      <!-- <ul>
        <li>For X drivers in the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li>In 2022, the average price of electricity in the US is expected to be 14.26 cents/kwh. (https://www.eia.gov/todayinenergy/detail.php?id=51438)
      <!-- <ul>
        <li>Across the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li style="word-wrap: break-word">In 2022, the US is expected to use 3.98 trillion kilowatt hours of electricity. (https://www.eia.gov/energyexplained/electricity/use-of-electricity.php#:~:text=Electricity%20consumption%20in%20the%20United,important%20to%20the%20U.S.%20economy.)
      <!-- <ul>
        <li>Across the USA, new car parking costs X per year, and existing parking loses X in real estate per year.</li>
      </ul> -->
    </li>
  </ul>
</div>

<h3><em>More coming soon ...</em></h3>
<p>Have policies to add?  Want to edit data?</p>
  <p><a href="https://docs.google.com/document/d/1w_QEqDER7GEi8Q8rOy1_RiOuT-iDZ7w20zgDESm8HSs/edit?usp=sharing">Add policies, edits, and suggestions</a>.</p>
  <hr>
  <p><a href="https://twitter.com/sambutlerUS">Twitter</p>
    <p>antiinflationary@sambutler.us</p>
</section>

<style>
  .policy {
    background: #f9f9f9;
    padding: 10px;
    border-radius: 10px;
    margin: auto;
  }

  .policies {
    padding: 10px;
  }

  h2 {
    margin-top: 0px;
  }

  * {
font-family: Inter var,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
  }

  p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}

.returns {
  color: green;
}

.invested {
  color: #301bed;
}

.policy li {
  margin-bottom: 10px;
}
</style>
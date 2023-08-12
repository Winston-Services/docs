<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Winston Holdings & Trust</title>
    <script
      src="https://cdn.ethers.io/lib/ethers-5.2.umd.min.js"
      type="application/javascript"
    ></script>
  </head>
  <body>
    <script src="https://d3js.org/d3.v4.js"></script>
    <script>
      var rickleInTrustBalance = 0;
      var rickleBurned = 0;
      var rickleLocked = 0;

      var DEAD = "0x000000000000000000000000000000000000dead";
      var TRUST = "0xF9B9eE3B0301B511cd5AA4b8D039F63df19C615a";
      var RICKLE = "0xeca15e1bbff172d545dd6325f3bae7b737906737";
      var WINSTON = "0x75578ebBefe274F240B8E1b5859cA34f342157D9";
      var AHWA = "0x3A81caafeeDCF2D743Be893858cDa5AcDBF88c11";
      var CAKE = "0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82";
      var BUSD = "0xe9e7CEA3DedcA5984780Bafc599bD69ADd087D56";
      var WBNB = "0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c";
      var USDT = "0x55d398326f99059fF775485246999027B3197955";
      var USDC = "0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d";
      var LIQUIDITY = [
        {
          dex: "PancakeSwap",
          token_1: "Rickle",
          token_2: "Winston",
          address: "0x"
        }
      ];
      async function main() {
        await bscHandler();
      }
      main();

      async function bscHandler() {
        const provider = new ethers.providers.JsonRpcProvider(
          "https://bsc-dataseed.binance.org/"
        );

        const rickleContract = new ethers.Contract(
          RICKLE,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const winstonContract = new ethers.Contract(
          WINSTON,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const ahwaContract = new ethers.Contract(
          AHWA,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const wbnbContract = new ethers.Contract(
          WBNB,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const cakeContract = new ethers.Contract(
          CAKE,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const busdContract = new ethers.Contract(
          BUSD,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const usdcContract = new ethers.Contract(
          USDC,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const usdtContract = new ethers.Contract(
          USDT,
          ["function balanceOf(address) view returns (uint)"],
          provider
        );

        const BSCTrustBNBBalance = await provider.getBalance(TRUST);
        document.getElementById("trust-bnb-balance").innerText =
          ethers.utils.formatEther(BSCTrustBNBBalance);

        const BSCWinstonBNBBalance = await provider.getBalance(WINSTON);
        document.getElementById("winston-bnb-balance").innerText =
          ethers.utils.formatEther(BSCWinstonBNBBalance);

        const BSCWinstonBurned = await winstonContract.balanceOf(DEAD);
        document.getElementById("burned-winston").innerText =
          ethers.utils.formatEther(BSCWinstonBurned);

        const BSCWinstonInWinston = await winstonContract.balanceOf(WINSTON);
        document.getElementById("locked-winston").innerText =
          ethers.utils.formatEther(BSCWinstonInWinston);

        const BSCWinstonInTrust = await winstonContract.balanceOf(TRUST);
        document.getElementById("winston-in-trust").innerText =
          ethers.utils.formatEther(BSCWinstonInTrust);

        const BSCRickleBurned = await rickleContract.balanceOf(DEAD);
        const BSCRickleInTrust = await rickleContract.balanceOf(TRUST);
        rickleInTrustBalance += BSCRickleInTrust;
        const BSCRickleInWinston = await winstonContract.balanceOf(RICKLE);

        document.getElementById("rickle-in-trust").innerText =
          ethers.utils.formatEther(rickleInTrustBalance);
      }
    </script>
    <header>
      <div class="top-navbar">
        <div class="winston-logo">
          <img src="winston-logo.png" />
        </div>
        <button>Trust Holdings</button>
        <button>ETH Holdings</button>
        <button>BSC Holdings</button>
        <button>POLY Holdings</button>
        <button>GNO Holdings</button>
        <button>ONE Holdings</button>
        <button>ARB Holdings</button>
        <button>Current Caretakers</button>
      </div>
    </header>
    <div class="page-content-wrapper">
      <div class="left-side">ltest</div>
      <div class="inner-page-content-wrapper" style="width: 80%">
        <div class="main-content">
          <section>
            <h3>Trust Overview</h3>
            Trust BNB <span id="trust-bnb-balance"></span><br />
            Trust WBNB <span id="trust-wbnb-balance"></span><br />
            Winston BNB <span id="winston-bnb-balance"></span><br />
            Winston WBNB <span id="winston-wbnb-balance"></span><br />

            <div class="trust-holdings">
              <div class="data-section" width="33%">
                <h3>Ahwa</h3>
                <div class="data-section-content">
                  <div class="data-section-left-side">
                    <!-- Create a div where the graph will take place -->
                    <div id="ahwa_data"></div>
                  </div>
                  <div class="data-section-right-side">
                    <table>
                      <tbody>
                        <tr>
                          <th>Total Supply</th>

                          <td>10,000</td>
                        </tr>
                        <tr>
                          <th>Burned</th>
                          <td></td>
                        </tr>
                        <tr>
                          <th>Locked</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Liquidity</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Circulating</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Held In Trust</th>
                          <td></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                <div class="data-section-content">test</div>
              </div>

              <div class="data-section" width="33%">
                <h3>Winston</h3>
                <div class="data-section-content">
                  <div class="data-section-left-side">
                    <!-- Create a div where the graph will take place -->
                    <div id="winston_data"></div>
                  </div>
                  <div class="data-section-right-side">
                    <table>
                      <tbody>
                        <tr>
                          <th>Total Supply</th>

                          <td>100,000,000</td>
                        </tr>
                        <tr>
                          <th>Burned</th>
                          <td><span id="burned-winston"></span></td>
                        </tr>
                        <tr>
                          <th>Locked</th>
                          <td><span id="locked-winston"></span></td>
                        </tr>

                        <tr>
                          <th>Liquidity</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Circulating</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Held In Trust</th>
                          <td><span id="winston-in-trust"></span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>

              <div class="data-section" width="33%">
                <h3>Rickle</h3>
                <div class="data-section-content">
                  <div class="data-section-left-side">
                    <!-- Create a div where the graph will take place -->
                    <div id="rickle_data"></div>
                  </div>
                  <div class="data-section-right-side">
                    <table>
                      <tbody>
                        <tr>
                          <th>Total Supply</th>

                          <td>100,000,000,000</td>
                        </tr>
                        <tr>
                          <th>Burned</th>
                          <td>50,197,856,814.6226</td>
                        </tr>
                        <tr>
                          <th>Locked</th>
                          <td>33,050,000</td>
                        </tr>

                        <tr>
                          <th>Liquidity</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Circulating</th>
                          <td></td>
                        </tr>

                        <tr>
                          <th>Held In Trust</th>
                          <td><span id="rickle-in-trust"></span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>
            </div>
          </section>
          <section>
            <div class="eth-holdings">
              <h3>ETH Chain Trust Holdings</h3>
            </div>
          </section>
          <section>
            <div class="bsc-holdings">
              <h3>Binance Smart Chain Trust Holdings</h3>
            </div>
          </section>
          <section>
            <div class="poly-holdings">
              <h3>Polygon Chain Trust Holdings</h3>
            </div>
          </section>
          <section>
            <div class="gno-holdings">
              <h3>Gnosis Chain Trust Holdings</h3>
            </div>
          </section>
          <section>
            <div class="one-holdings">
              <h3>Harmony One Chain Trust Holdings</h3>
            </div>
          </section>
          <section>
            <div class="arb-holdings">
              <h3>Arbitrum Chain Trust Holdings</h3>
            </div>
          </section>
          <section>
            <div class="current-caretakers">
              <h3>Current Caretakers</h3>
              <div class="caretaker-wrapper"></div>
            </div>
          </section>
        </div>
      </div>
      <div class="right-side">rtest</div>
    </div>

    <footer>
      <div class="footer">Copyright © 2023 All Rights Reserved.</div>
    </footer>
    <style>
      html,
      body {
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
      }
      .winston-logo {
        padding: 0px;
        margin: 0px;
        width: 36px;
      }
      .top-navbar > button {
        color: rgb(46, 46, 240);
      }
      .page-content-wrapper {
        display: flex;
        flex-direction: row;
        align-content: flex-start;
        justify-content: space-between;
        flex-wrap: wrap;
      }

      .page-content-wrapper div {
        justify-content: flex-start;
      }

      .trust-holdings {
        width: 100%;
        display: flex;
        flex-direction: row;
      }

      .main-content,
      section {
        width: 100%;
      }

      .data-section-content {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-content: flex-start;
        justify-content: space-between;
        align-items: stretch;
        width: 100%;
      }

      .data-section {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-content: flex-start;
        justify-content: space-between;
        width: 100%;
      }

      footer {
        text-align: center;
      }
    </style>
    <script>
      function drawPieGraph(
        id = "#my_dataviz",
        width = 450,
        height = 450,
        margin = 40,
        data,
        colors = []
      ) {
        // The radius of the pieplot is half the width or half the height (smallest one). I subtract a bit of margin.
        var radius = Math.min(width, height) / 2 - margin;

        // append the svg object to the div called 'my_dataviz'
        var svg = d3
          .select(id)
          .append("svg")
          .attr("width", width)
          .attr("height", height)
          .append("g")
          .attr("transform", "translate(" + width / 2 + "," + height / 2 + ")");

        // set the color scale
        var color = d3.scaleOrdinal().domain(data).range(colors);

        // Compute the position of each group on the pie:
        var pie = d3.pie().value(function (d) {
          return d.value;
        });
        var data_ready = pie(d3.entries(data));

        // Build the pie chart: Basically, each part of the pie is a path that we build using the arc function.
        svg
          .selectAll("whatever")
          .data(data_ready)
          .enter()
          .append("path")
          .attr("d", d3.arc().innerRadius(0).outerRadius(radius))
          .attr("fill", function (d) {
            return color(d.data.key);
          })
          .attr("stroke", "black")
          .style("stroke-width", "2px")
          .style("opacity", 0.7);
      }
      drawPieGraph(
        "#rickle_data",
        140,
        140,
        4,
        {
          burns: 50197856814.6226,
          locked: 33050000,
          liquidity: 0,
          circulating: 0,
          intrust: 0
        },
        ["red", "orange", "green", "gold", "purple"]
      );

      drawPieGraph(
        "#winston_data",
        140,
        140,
        4,
        {
          burns: 50000,
          locked: 50000000,
          liquidity: 0,
          circulating: 0,
          intrust: 0
        },
        ["red", "orange", "green", "gold", "purple"]
      );

      drawPieGraph(
        "#ahwa_data",
        140,
        140,
        4,
        { burns: 100, locked: 50, liquidity: 20, circulating: 25, intrust: 25 },
        ["red", "orange", "green", "gold", "purple"]
      );

      drawPieGraph(
        "#winston_academy_coin_data",
        140,
        140,
        4,
        { burns: 100, locked: 50, liquidity: 20, circulating: 25, intrust: 25 },
        ["red", "orange", "green", "gold", "purple"]
      );
    </script>
  </body>
</html>

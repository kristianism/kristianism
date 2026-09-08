<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://capsule-render.vercel.app/api?type=rect&color=0:0d1117%2C100:161b22&height=150&section=header&text=Kristian&fontSize=56&fontColor=c9d1d9&fontAlignY=50&desc=financial%20systems%20developer&descSize=15&descAlignY=76&descColor=58A6FF" />
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:f6f8fa%2C100:eaeef2&height=150&section=header&text=Kristian&fontSize=56&fontColor=1f2328&fontAlignY=50&desc=financial%20systems%20developer&descSize=15&descAlignY=76&descColor=0969da" width="100%" alt="Kristian, financial systems developer" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=17&duration=3200&pause=1200&color=58A6FF&center=true&vCenter=true&width=760&height=40&lines=Protocol+engineering+%C2%B7+DeFi+architecture;Forensic+accounting+%C2%B7+On-chain+security;Auditable+financial+infrastructure%2C+on-chain+and+off" />
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=17&duration=3200&pause=1200&color=0969DA&center=true&vCenter=true&width=760&height=40&lines=Protocol+engineering+%C2%B7+DeFi+architecture;Forensic+accounting+%C2%B7+On-chain+security;Auditable+financial+infrastructure%2C+on-chain+and+off" alt="Protocol engineering, DeFi architecture, forensic accounting, on-chain security" />
</picture>

</div>

<img src="./img/linebreak.gif" width="100%" height="8" alt="" />

## I build financial systems that can prove they are correct

I'm Kristian, a financial systems developer working where capital, code, and security meet. I design and ship auditable on-chain and off-chain financial infrastructure: Solidity protocols, corporate treasury automation, and the monitoring and forensic tooling needed to explain every movement of funds after the fact.

I hold CrFA and CFC credentials and a BS in Management Accounting, so the accounting rigor is part of the design, not a review step at the end. In practice that means smart contracts where a rounding error is a liability, treasury flows that reconcile by default, and monitoring that surfaces failures while they are still actionable.

<table>
  <tr>
    <td width="160"><b>Focus</b></td>
    <td>Protocol engineering, DeFi architecture, forensic accounting, on-chain security</td>
  </tr>
  <tr>
    <td><b>Credentials</b></td>
    <td>CrFA · CFC · BS Management Accounting</td>
  </tr>
  <tr>
    <td><b>Core stack</b></td>
    <td>Solidity, Foundry, Hardhat · TypeScript, Node.js, Next.js, React · Python · n8n, Xero, PostgreSQL</td>
  </tr>
  <tr>
    <td><b>Availability</b></td>
    <td>Selectively available for protocol engineering, security reviews, and DeFi build or advisory engagements</td>
  </tr>
  <tr>
    <td><b>Contact</b></td>
    <td><a href="https://x.com/0xKristianity">X</a> · <a href="https://t.me/thisiskristian">Telegram</a> · <a href="https://discord.com/users/iamkristian">Discord</a></td>
  </tr>
</table>

## Selected work

Public repositories, described from their own READMEs. Status lines state exactly what has and has not been reviewed or deployed.

<table>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/kristianism/zero-balance-sweep-module">Zero-Balance Corporate Sweep Module</a></h3>
      <p><code>Solidity 0.8.24</code> <code>Foundry</code> <code>Safe</code> <code>Aave V3</code></p>
      <p>A Safe module that sweeps idle ERC-20 operating balances above a threshold into Aave V3 and withdraws exact shortfalls just in time for planned payments.</p>
      <ul>
        <li>Relayer JIT withdrawals require a Safe-set, amount-bound, expiring intent. Relayers can top up the Safe but never execute payments.</li>
        <li>Per-call sweep caps, JIT caps, and a shared relayer cooldown. Validates aToken wiring and Pool reserve registration. No <code>delegatecall</code>.</li>
        <li>Unit, fuzz, invariant, Ethereum mainnet-fork, and Safe v1.4.1 proxy integration tests.</li>
      </ul>
      <p><sub><b>Status:</b> reference implementation with an internal security review. No independent professional audit.</sub></p>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/kristianism/the-factory">The Factory</a></h3>
      <p><code>Solidity 0.8.36</code> <code>Foundry</code> <code>OpenZeppelin 5</code></p>
      <p>A smart contract toolkit of small, readable templates created as minimal proxy clones from paused-by-default factories: ERC-20 (standard and tax), ERC-721, vesting wallets, registration and Merkle airdrops, and staking reward farms.</p>
      <ul>
        <li>Two-step ownership acceptance across factories and clones, ERC-2612 permit on the ERC-20, and an owner-controlled UUPS fee collector.</li>
        <li>Documented security review with twelve findings patched and each tied to a named regression test, including reward-as-principal drains, taxed-deposit liabilities, and donation dilution.</li>
      </ul>
      <p><sub><b>Status:</b> contract repository, not a finished product. Manual review plus Foundry regression and fuzz tests; not an independent audit. No deployment of the patched release has been performed.</sub></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/kristianism/discord-n8n-bridge">Discord to n8n Bridge</a></h3>
      <p><code>TypeScript</code> <code>Node.js 20</code> <code>Docker</code></p>
      <p>A persistent service that holds a Discord Gateway connection, normalizes created and edited messages into a versioned JSON envelope, and delivers them to an n8n webhook that owns routing.</p>
      <ul>
        <li>Idempotency keys per create and edit, exponential backoff with jitter that honors <code>Retry-After</code>, and bounded in-flight deliveries with load shedding.</li>
        <li>Guild and channel allowlists, bot and webhook loop prevention, redacted structured logs, and graceful shutdown that drains in-flight deliveries.</li>
      </ul>
      <p><sub><b>Status:</b> deployable service, one instance per bot and n8n webhook, configured entirely through environment variables.</sub></p>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/kristianism/defi-yield-farm">DeFi Yield Farm</a></h3>
      <p><code>Solidity 0.8.20</code> <code>OpenZeppelin</code> <code>MasterChef</code></p>
      <p>A MasterChef-style staking template that distributes any elected ERC-20 as the reward token.</p>
      <ul>
        <li>Per-second emissions with a transparent <code>updateEmissionRate</code> instead of hidden dummy pools; configurable allocation points and deposit fees.</li>
        <li><code>pendingReward</code> view, <code>emergencyWithdraw</code>, ReentrancyGuard, and SafeERC20 reward transfers.</li>
      </ul>
      <p><sub><b>Status:</b> template and earlier work, last updated March 2025.</sub></p>
    </td>
  </tr>
</table>

## What I work on

<table>
  <tr>
    <td width="220" valign="top"><b>Protocol &amp; smart contracts</b></td>
    <td>Solidity systems for yield, launchpads, bonding curves, account modules, and Safe modules.</td>
  </tr>
  <tr>
    <td valign="top"><b>Treasury &amp; automation</b></td>
    <td>On-chain corporate treasury, zero-balance sweeps, Just-In-Time OpEx funding, and n8n and Xero financial workflows.</td>
  </tr>
  <tr>
    <td valign="top"><b>Security &amp; forensics</b></td>
    <td>Threat modeling, on-chain monitoring, smart contract review, forensic accounting, and investigation.</td>
  </tr>
  <tr>
    <td valign="top"><b>Full-stack delivery</b></td>
    <td>Next.js and React dashboards, Web3 frontends, TypeScript and Node.js services, shipped end to end.</td>
  </tr>
</table>

## Stack

<table>
  <tr>
    <td width="220" valign="top"><b>Smart contracts</b></td>
    <td>
      <img src="./img/Solidity.svg" width="40" height="40" alt="Solidity" />&nbsp;
      <img src="./img/foundry.png" width="40" height="40" alt="Foundry" />&nbsp;
      <img src="./img/hardhat-original.svg" width="40" height="40" alt="Hardhat" />
      <br /><sub>Solidity · Foundry · Hardhat</sub>
    </td>
  </tr>
  <tr>
    <td valign="top"><b>Languages</b></td>
    <td>
      <img src="./img/TypeScript.svg" width="40" height="40" alt="TypeScript" />&nbsp;
      <img src="./img/JavaScript.svg" width="40" height="40" alt="JavaScript" />&nbsp;
      <img src="./img/Python-Dark.svg" width="40" height="40" alt="Python" />&nbsp;
      <img src="./img/CSS.svg" width="40" height="40" alt="CSS" />
      <br /><sub>TypeScript · JavaScript · Python · CSS</sub>
    </td>
  </tr>
  <tr>
    <td valign="top"><b>Full-stack</b></td>
    <td>
      <img src="./img/nextjs-original.svg" width="40" height="40" alt="Next.js" />&nbsp;
      <img src="./img/React-Dark.svg" width="40" height="40" alt="React" />&nbsp;
      <img src="./img/TailwindCSS-Dark.svg" width="40" height="40" alt="Tailwind CSS" />&nbsp;
      <img src="./img/NodeJS-Dark.svg" width="40" height="40" alt="Node.js" />
      <br /><sub>Next.js · React · Tailwind CSS · Node.js</sub>
    </td>
  </tr>
  <tr>
    <td valign="top"><b>Automation &amp; data</b></td>
    <td>
      <img src="https://img.shields.io/badge/n8n-101216?style=flat-square&logo=n8n&logoColor=EA4B71" alt="n8n" />
      <img src="https://img.shields.io/badge/PostgreSQL-101216?style=flat-square&logo=postgresql&logoColor=4F90D0" alt="PostgreSQL" />
      <img src="https://img.shields.io/badge/Xero-101216?style=flat-square&logo=xero&logoColor=13B5EA" alt="Xero" />
      <img src="https://img.shields.io/badge/QuickBooks-101216?style=flat-square&logo=intuit&logoColor=2CA01C" alt="QuickBooks" />
      <br /><sub>n8n · PostgreSQL · Xero · QuickBooks</sub>
    </td>
  </tr>
  <tr>
    <td valign="top"><b>Tooling</b></td>
    <td>
      <img src="./img/VSCode-Dark.svg" width="40" height="40" alt="Visual Studio Code" />&nbsp;
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" width="40" height="40" alt="Docker" />&nbsp;
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/raspberrypi/raspberrypi-original.svg" width="40" height="40" alt="Raspberry Pi" />
      <br /><sub>Visual Studio Code · Docker · Raspberry Pi</sub>
    </td>
  </tr>
</table>

## Operating principles

<table>
  <tr>
    <td width="280" valign="top"><code>01</code> <b>Correctness over cleverness</b></td>
    <td>Exact shortfall math, immutable non-upgradeable modules, pinned dependencies, and no <code>delegatecall</code> where a plain call will do.</td>
  </tr>
  <tr>
    <td valign="top"><code>02</code> <b>Audit trails by default</b></td>
    <td>Events treated as operational evidence and reconciled against token transfers and balances. Structured logs that redact secrets and message content.</td>
  </tr>
  <tr>
    <td valign="top"><code>03</code> <b>Threat model first</b></td>
    <td>Contract repositories document the trust model and each actor's authority alongside the interface. Contributions need a threat model and regression tests to be considered.</td>
  </tr>
  <tr>
    <td valign="top"><code>04</code> <b>Composable over bespoke</b></td>
    <td>Safe modules instead of custom wallets, minimal proxy clones instead of one-off deployments, n8n as the routing layer instead of hand-rolled workflow code.</td>
  </tr>
  <tr>
    <td valign="top"><code>05</code> <b>Measure what ships</b></td>
    <td>Unit, fuzz, invariant, and mainnet-fork tests. Each security finding is closed with a named regression test, and each README states what the tests do not cover.</td>
  </tr>
</table>

## Activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com/?user=kristianism&theme=github-dark-blue&hide_border=true&date_format=M%20j%5B%2C%20Y%5D&ring=58A6FF&fire=58A6FF&currStreakLabel=58A6FF" />
  <img src="https://streak-stats.demolab.com/?user=kristianism&theme=default&hide_border=true&date_format=M%20j%5B%2C%20Y%5D&ring=0969DA&fire=0969DA&currStreakLabel=0969DA&background=FFFFFF" alt="GitHub contribution streak for kristianism" />
</picture>

</div>

<img src="./img/linebreak.gif" width="100%" height="8" alt="" />

## Contact

<div align="center">

Building something where capital meets code, or need a second pair of eyes on one? Reach out.

<a href="https://x.com/0xKristianity"><img src="https://img.shields.io/badge/X-0d1117?style=for-the-badge&logo=x&logoColor=c9d1d9" alt="X, @0xKristianity" /></a>&nbsp;&nbsp;<a href="https://t.me/thisiskristian"><img src="https://img.shields.io/badge/Telegram-0d1117?style=for-the-badge&logo=telegram&logoColor=58A6FF" alt="Telegram, @thisiskristian" /></a>&nbsp;&nbsp;<a href="https://discord.com/users/iamkristian"><img src="https://img.shields.io/badge/Discord-0d1117?style=for-the-badge&logo=discord&logoColor=58A6FF" alt="Discord, iamkristian" /></a>

</div>

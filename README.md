# vortex-investment-<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vortex Investment</title>
<style>
  body {
    background: #0a0a0a;
    color: #fff;
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px 20px 80px;
  }
  h1, h2, h3 { color: #d40000; text-align: center; margin: 20px 0 10px; }
.container { max-width: 900px; margin: 0 auto; }
.hidden { display: none!important; }
.topbar { display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; }
.logout-btn { background: #333; color: #fff; border: 1px solid #d40000; padding: 8px 14px; border-radius: 8px; cursor: pointer; font-size: 13px; }
.logout-btn:hover { background: #d40000; }
.stats-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin: 15px 0; }
.stat-card { background: #1a1a1a; border: 2px solid #d40000; border-radius: 12px; padding: 15px; text-align: center; }
.stat-card h4 { margin: 0 0 8px; font-size: 13px; color: #aaa; }
.stat-card p { margin: 0; font-size: 22px; font-weight: bold; color: #d40000; }
.referral-box,.bank-box,.daily-box { background: #1a1a1a; border: 2px dashed #d40000; border-radius: 12px; padding: 15px; margin: 15px 0; text-align: center; }
.referral-link-wrap { display: flex; gap: 8px; margin-top: 10px; }
.referral-link-wrap input { flex: 1; padding: 10px; background: #0a0a0a; border: 2px solid #333; border-radius: 8px; color: #fff; font-size: 14px; }
.badge { padding: 4px 8px; border-radius: 6px; font-size: 12px; font-weight: bold; }
.badge.success { background: #25D366; color: #000; }
.badge.pending { background: #ffaa00; color: #000; }
.badge.claimed { background: #666; color: #fff; }
.auth-wrap { background: #1a1a1a; border: 2px solid #d40000; border-radius: 12px; padding: 20px; margin: 20px 0; }
.tab-btns { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 15px; }
.tab-btn { background: #111; border: 2px solid #333; color: #fff; padding: 12px; font-weight: bold; border-radius: 10px; cursor: pointer; transition: 0.2s; }
.tab-btn.active { background: #d40000; border-color: #ff1a1a; }
.auth-form { display: none; }
.auth-form.active { display: block; animation: fadeIn 0.3s ease; }
.input-group { margin: 12px 0; }
.input-group label { display: block; font-size: 14px; margin-bottom: 6px; color: #aaa; }
.input-group input { width: 100%; padding: 12px; background: #0a0a0a; border: 2px solid #333; border-radius: 8px; color: #fff; font-size: 15px; box-sizing: border-box; }
.input-group input:focus { border-color: #d40000; outline: none; }
.auth-btn { width: 100%; background: #d40000; color: #fff; border: none; padding: 14px; border-radius: 10px; font-weight: bold; font-size: 16px; margin-top: 10px; cursor: pointer; transition: 0.2s; }
.auth-btn:hover { background: #ff1a1a; }
.auth-btn:disabled { background: #333; cursor: not-allowed; }
.small-text { text-align: center; font-size: 13px; color: #aaa; margin-top: 10px; }
table { width: 100%; border-collapse: collapse; margin: 15px 0; font-size: 14px; overflow-x: auto; display: block; }
th, td { border: 1px solid #333; padding: 10px; text-align: center; white-space: nowrap; }
th { background: #d40000; color: #fff; font-weight: bold; }
tr:nth-child(even) td { background: #1a1a1a; }
tr:nth-child(odd) td { background: #111; }
.terms-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin: 20px 0; }
.box { background: #1a1a1a; border: 2px solid #d40000; border-radius: 12px; padding: 15px; }
.box p { margin: 8px 0; font-size: 15px; }
.box span { color: #d40000; font-weight: bold; }
.amount-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; margin: 15px 0; }
.amount-btn { background: #1a1a1a; border: 2px solid #d40000; color: #fff; padding: 15px; font-size: 16px; font-weight: bold; border-radius: 10px; cursor: pointer; transition: 0.2s; }
.amount-btn:hover,.amount-btn.active { background: #d40000; border-color: #ff1a1a; }
.account-box,.withdraw-box { display: none; background: #1a1a1a; border: 2px solid #d40000; border-radius: 12px; padding: 20px; margin-top: 15px; animation: fadeIn 0.3s ease; }
@keyframes fadeIn { from {opacity: 0; transform: translateY(10px);} to {opacity: 1; transform: translateY(0);} }
.account-line,.calc-line { margin: 12px 0; font-size: 16px; display: flex; align-items: center; flex-wrap: wrap; justify-content: space-between; }
.account-line span,.calc-line span { color: #d40000; font-weight: bold; }
.copy-btn { background: #d40000; color: #fff; border: none; padding: 6px 10px; border-radius: 6px; font-size: 13px; margin-left: 8px; cursor: pointer; transition: 0.2s; }
.copy-btn:hover { background: #ff1a1a; }
.support-btns { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 15px; }
.whatsapp-btn,.telegram-btn { display: block; color: #fff; text-align: center; padding: 14px; border-radius: 10px; font-weight: bold; text-decoration: none; font-size: 15px; transition: 0.2s; }
.whatsapp-btn { background: #25D366; }
.whatsapp-btn:hover { background: #1ebe5b; }
.telegram-btn { background: #0088cc; }
.telegram-btn:hover { background: #006ba3; }
.upload-btn { display: block; background: #d40000; color: #fff; text-align: center; padding: 14px; border-radius: 10px; font-weight: bold; font-size: 15px; margin-top: 10px; cursor: pointer; border: none; width: 100%; transition: 0.2s; }
.upload-btn:hover { background: #ff1a1a; }
#fileName { margin-top: 8px; font-size: 13px; color: #aaa; text-align: center; }
.bottom-nav { position: fixed; bottom: 0; left: 0; right: 0; background: #111; border-top: 2px solid #d40000; display: grid; grid-template-columns: repeat(4, 1fr); z-index: 999; }
.nav-btn { background: none; border: none; color: #aaa; padding: 12px 5px; font-size: 12px; cursor: pointer; text-align: center; transition: 0.2s; }
.nav-btn.active { color: #d40000; font-weight: bold; }
.nav-btn span { display: block; font-size: 20px; margin-bottom: 3px; }
.withdraw-presets { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin: 15px 0; }
.withdraw-preset-btn { background: #1a1a1a; border: 2px solid #d40000; color: #fff; padding: 12px; font-size: 14px; font-weight: bold; border-radius: 10px; cursor: pointer; transition: 0.2s; }
.withdraw-preset-btn:hover,.withdraw-preset-btn.active { background: #d40000; border-color: #ff1a1a; }
@media (max-width: 600px) {
.terms-grid { grid-template-columns: 1fr; }
table { font-size: 12px; }
.support-btns { grid-template-columns: 1fr; }
.stats-grid { grid-template-columns: 1fr; }
.withdraw-presets { grid-template-columns: repeat(2, 1fr); }
}
</style>
</head>
<body>

<div class="container">
  <h1>VORTEX INVESTMENT</h1>

  <div class="auth-wrap" id="authSection">
    <div class="tab-btns">
      <button class="tab-btn active" onclick="switchTab('register')">Register</button>
      <button class="tab-btn" onclick="switchTab('login')">Login</button>
    </div>
    <form class="auth-form active" id="registerForm">
      <h3>Create Account</h3>
      <div class="input-group"><label>Full Name</label><input type="text" id="regName" placeholder="John Doe" required></div>
      <div class="input-group"><label>Phone Number</label><input type="tel" placeholder="080xxxxxxxx" required></div>
      <div class="input-group"><label>Email</label><input type="email" placeholder="you@email.com" required></div>
      <div class="input-group"><label>Password</label><input type="password" placeholder="Min 6 characters" required></div>
      <div class="input-group"><label>Referrer Code [Optional]</label><input type="text" placeholder="VRTX123"></div>
      <button type="submit" class="auth-btn">Register Now</button>
      <p class="small-text">By registering, you agree to our terms.</p>
    </form>
    <form class="auth-form" id="loginForm">
      <h3>Welcome Back</h3>
      <div class="input-group"><label>Phone or Email</label><input type="text" placeholder="080xxxxxxxx or email" required></div>
      <div class="input-group"><label>Password</label><input type="password" placeholder="Your password" required></div>
      <button type="submit" class="auth-btn">Login</button>
      <p class="small-text">Forgot password? Contact support.</p>
    </form>
  </div>

  <div id="dashboard" class="hidden">
    <div class="topbar"><h2 style="margin:0; text-align:left;">Dashboard</h2><button class="logout-btn" onclick="logout()">Logout</button></div>

    <div id="page-home">
      <div class="stats-grid">
        <div class="stat-card"><h4>Account Balance</h4><p id="balance">₦200</p></div>
        <div class="stat-card"><h4>Referral Balance</h4><p id="refBalance">₦0</p></div>
        <div class="stat-card"><h4>Welcome Bonus</h4><p>₦200</p></div>
      </div>
      <div class="daily-box"><h3>Daily Login Reward</h3><p>Claim <span style="color:#d40000; font-weight:bold;">₦100</span> every 24 hours</p><button class="auth-btn" id="dailyBtn" onclick="claimDaily()">🎁 Claim ₦100</button><p class="small-text" id="dailyTimer"></p></div>
      <div class="bank-box"><h3>Bank Account Details</h3>
        <div class="input-group"><label>Bank Name</label><input type="text" id="bankName" placeholder="e.g Opay, UBA, GTBank"></div>
        <div class="input-group"><label>Account Number</label><input type="number" id="bankAcc" placeholder="10 digit account number"></div>
        <div class="input-group"><label>Account Name</label><input type="text" id="bankHolder" placeholder="Account holder name"></div>
        <button class="auth-btn" onclick="saveBank()">💾 Save Bank Details</button><p class="small-text" id="bankSavedText"></p>
      </div>
      <h2>VORTEX INVESTMENT PLANS</h2>
      <table><thead><tr><th>Plan</th><th>Price</th><th>Daily Earnings</th><th>Total Earnings</th><th>Duration</th></tr></thead>
      <tbody><tr><td>Vortex 1</td><td>3,000</td><td>1,000</td><td>50,000</td><td>50 days</td></tr>
      <tr><td>Vortex 2</td><td>5,000</td><td>2,050</td><td>123,000</td><td>60 days</td></tr>
      <tr><td>Vortex 3</td><td>8,000</td><td>3,500</td><td>210,000</td><td>60 days</td></tr>
      <tr><td>Vortex 4</td><td>20,000</td><td>6,500</td><td>585,000</td><td>90 days</td></tr>
      <tr><td>Vortex 5</td><td>45,000</td><td>10,090</td><td>908,100</td><td>90 days</td></tr>
      <tr><td>Vortex 6</td><td>60,000</td><td>17,000</td><td>1,530,000</td><td>90 days</td></tr>
      <tr><td>Vortex 7</td><td>90,000</td><td>27,000</td><td>2,430,000</td><td>90 days</td></tr>
      <tr><td>Vortex 8</td><td>200,000</td><td>57,500</td><td>5,175,000</td><td>90 days</td></tr>
      <tr><td>Vortex 9</td><td>350,000</td><td>90,000</td><td>32,040,000</td><td>356 days</td></tr>
      <tr><td>Vortex 10</td><td>500,000</td><td>175,000</td><td>62,300,000</td><td>356 days</td></tr></tbody></table>
      <div class="terms-grid">
        <div class="box"><h3>Other Terms</h3><p>Welcome Bonus: <span>200</span></p><p>Minimum Deposit: <span>3,000</span></p><p>Minimum Withdrawal: <span>500</span></p><p>Withdrawal Charges: <span>17%</span></p><p>Withdrawal Time: <span>7:00am to 7:30pm</span></p><p>Daily Login: <span>100</span></p></div>
        <div class="box"><h3>Referral Bonus</h3><p>Level 1: <span>35%</span></p><p>Level 2: <span>10%</span></p><p>Level 3: <span>5%</span></p></div>
      </div>
      <h2 style="margin-top:30px;">Transaction History</h2>
      <div style="display:flex; justify-content:space-between; align-items:center;"><p class="small-text" style="margin:0;">All activities are saved locally</p><button class="copy-btn" onclick="clearHistory()">Clear</button></div>
      <table id="historyTable"><thead><tr><th>Date</th><th>Type</th><th>Amount</th><th>Status</th><th>Balance</th></tr></thead><tbody id="historyBody"><tr><td colspan="5">No transactions yet</td></tr></tbody></table>
    </div>

    <div id="page-deposit" class="hidden">
      <h2>Recharge</h2>
      <div class="amount-grid">
        <button class="amount-btn" data-amount="3,000">₦3,000</button><button class="amount-btn" data-amount="5,000">₦5,000</button>
        <button class="amount-btn" data-amount="8,000">₦8,000</button><button class="amount-btn" data-amount="20,000">₦20,000</button>
        <button class="amount-btn" data-amount="45,000">₦45,000</button><button class="amount-btn" data-amount="60,000">₦60,000</button>
        <button class="amount-btn" data-amount="90,000">₦90,000</button><button class="amount-btn" data-amount="200,000">₦200,000</button>
        <button class="amount-btn" data-amount="350,000">₦350,000</button><button class="amount-btn" data-amount="500,000">₦500,000</button>
      </div>
      <div class="account-box" id="accountBox">
        <h3>Transfer Details</h3>
        <div class="account-line">Amount: <span id="selectedAmount">₦0</span></div>
        <div class="account-line">ACCOUNT NUMBER: <span id="accNo">9977784080</span><button class="copy-btn" onclick="copyText('accNo')">Copy</button></div>
        <div class="account-line">BANK NAME: <span>Blooms microfinance bank</span></div>
        <div class="account-line">NAME: <span>Virtual account(Roqqu Nigeria Limited)</span></div>
        <div class="support-btns"><a id="whatsappLink" href="https://wa.me/2349061933712" target="_blank" class="whatsapp-btn">📱 WhatsApp Support</a><a id="telegramLink" href="https://t.me/mr_realfake247" target="_blank" class="telegram-btn">✈️ Telegram Support</a></div>
        <input type="file" id="proofUpload" accept="image/*" style="display:none;" onchange="updateSupportLinks()">
        <button class="upload-btn" onclick="document.getElementById('proofUpload').click()">📤 Upload Proof of Payment</button>
        <div id="fileName"></div>
        <button class="auth-btn" id="confirmRechargeBtn" style="margin-top:12px;">✅ Submit Deposit Request (Pending)</button>
      </div>
    </div>

    <div id="page-team" class="hidden">
      <div class="referral-box"><h3>Referral Program</h3><p>Invite friends and earn for life</p><p>Level 1: <span style="color:#d40000; font-weight:bold;">35%</span> | Level 2: <span style="color:#d40000; font-weight:bold;">10%</span> | Level 3: <span style="color:#d40000; font-weight:bold;">5%</span></p>
      <div class="referral-link-wrap"><input type="text" id="refLink" readonly><button class="copy-btn" onclick="copyRef()">Copy</button></div>
      <button class="auth-btn" style="background:#333; margin-top:10px;" onclick="fakeRefCredit()">+₦1000 Test Referral Credit</button></div>
    </div>

    <div id="page-withdraw" class="hidden">
      <h2>Withdraw</h2>
      <div class="withdraw-box" id="withdrawBox" style="display:block;">
        <div class="withdraw-presets">
          <button class="withdraw-preset-btn" data-amount="500">₦500</button>
          <button class="withdraw-preset-btn" data-amount="1000">₦1,000</button>
          <button class="withdraw-preset-btn" data-amount="1500">₦1,500</button>
          <button class="withdraw-preset-btn" data-amount="3000">₦3,000</button>
          <button class="withdraw-preset-btn" data-amount="max">MAX</button>
        </div>
        <div class="input-group"><label>Withdrawal Amount [Min: ₦500]</label><input type="number" id="withdrawAmount" placeholder="Enter amount" min="500"></div>
        <div class="calc-line">Withdrawal Charge 17%: <span id="withdrawCharge">₦0</span></div>
        <div class="calc-line">You will receive: <span id="withdrawNet">₦0</span></div>
        <div class="calc-line" id="withdrawToAccount" style="font-size:13px; color:#aaa;"></div>
        <button class="auth-btn" id="withdrawBtn">💸 Withdraw Now</button>
        <p class="small-text">Withdrawal Time: 7:00am to 7:30pm Daily</p>
      </div>
    </div>
  </div>
</div>

<div class="bottom-nav hidden" id="bottomNav">
  <button class="nav-btn active" onclick="showPage('home')"><span>🏠</span>Home</button>
  <button class="nav-btn" onclick="showPage('deposit')"><span>💰</span>Deposit</button>
  <button class="nav-btn" onclick="showPage('team')"><span>👥</span>Team</button>
  <button class="nav-btn" onclick="showPage('withdraw')"><span>💸</span>Withdraw</button>
</div>

<script>
  let selectedAmt = "₦0";
  let uploadedFile = "";
  let balance = 200;
  let refBalance = 0;
  let userName = "Guest";
  let history = [];
  let currentPage = 'home';
  const WITHDRAW_CHARGE = 0.17;
  const MIN_WITHDRAW = 500;
  const DAILY_AMOUNT = 100;

  const authSection = document.getElementById('authSection');
  const dashboard = document.getElementById('dashboard');
  const bottomNav = document.getElementById('bottomNav');
  const balanceEl = document.getElementById('balance');
  const refBalanceEl = document.getElementById('refBalance');
  const refLink = document.getElementById('refLink');
  const withdrawAmount = document.getElementById('withdrawAmount');
  const withdrawCharge = document.getElementById('withdrawCharge');
  const withdrawNet = document.getElementById('withdrawNet');
  const withdrawToAccount = document.getElementById('withdrawToAccount');
  const historyBody = document.getElementById('historyBody');
  const dailyBtn = document.getElementById('dailyBtn');
  const dailyTimer = document.getElementById('dailyTimer');

  function showPage(page) {
    document.querySelectorAll('#dashboard > div[id^=page-]').forEach(p => p.classList.add('hidden'));
    document.getElementById('page-'+page).classList.remove('hidden');
    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
    document.querySelectorAll('.nav-btn')[['home','deposit','team','withdraw'].indexOf(page)].classList.add('active');
    currentPage = page;
    if(page === 'withdraw') updateBankText();
  }

  function loadData() {
    balance = parseInt(localStorage.getItem('vortex_balance')) || 200;
    refBalance = parseInt(localStorage.getItem('vortex_ref')) || 0;
    userName = localStorage.getItem('vortex_name') || 'Guest';
    history = JSON.parse(localStorage.getItem('vortex_history')) || [];
    balanceEl.textContent = '₦' + balance.toLocaleString();
    refBalanceEl.textContent = '₦' + refBalance.toLocaleString();
    refLink.value = `https://vortex.com/?ref=${userName.replace(/\s+/g,'').toUpperCase()}`;
    document.getElementById('bankName').value = localStorage.getItem('vortex_bank') || '';
    document.getElementById('bankAcc').value = localStorage.getItem('vortex_acc') || '';
    document.getElementById('bankHolder').value = localStorage.getItem('vortex_holder') || '';
    updateBankText();
    renderHistory();
    checkDailyStatus();
  }
  function saveData() {
    localStorage.setItem('vortex_balance', balance);
    localStorage.setItem('vortex_ref', refBalance);
    localStorage.setItem('vortex_history', JSON.stringify(history));
    balanceEl.textContent = '₦' + balance.toLocaleString();
    refBalanceEl.textContent = '₦' + refBalance.toLocaleString();
  }
  function addHistory(type, amount, status) {
    const now = new Date().toLocaleString('en-NG');
    history.unshift({date: now, type, amount, status, bal: balance});
    if(history.length > 20) history.pop();
    saveData();
    renderHistory();
  }
  function renderHistory() {
    if(history.length === 0) { historyBody.innerHTML = `<tr><td colspan="5">No transactions yet</td></tr>`; return; }
    historyBody.innerHTML = history.map(h => `<tr><td>${h.date}</td><td>${h.type}</td><td>₦${h.amount.toLocaleString()}</td><td><span class="badge ${h.status==='Success'?'success':'pending'}">${h.status}</span></td><td>₦${h.bal.toLocaleString()}</td></tr>`).join('');
  }
  function clearHistory() { if(confirm('Clear all history?')) { history = []; localStorage.removeItem('vortex_history'); renderHistory(); } }

  function checkDailyStatus() {
    const lastClaim = parseInt(localStorage.getItem('vortex_daily')) || 0;
    const now = Date.now();
    const diff = now - lastClaim;
    const dayMs = 24*60*60*1000;
    if(diff < dayMs) { dailyBtn.disabled = true; dailyBtn.textContent = '✅ Claimed Today'; dailyBtn.classList.add('claimed'); updateTimer(dayMs - diff); }
    else { dailyBtn.disabled = false; dailyBtn.textContent = '🎁 Claim ₦100'; dailyBtn.classList.remove('claimed'); dailyTimer.textContent = ''; }
  }
  function updateTimer(ms) { const h = Math.floor(ms/1000/60/60); const m = Math.floor(ms/1000/60)%60; dailyTimer.textContent = `Next: ${h}h ${m}m`; if(ms > 0) setTimeout(() => updateTimer(ms-60000), 60000); }
  function claimDaily() { balance += DAILY_AMOUNT; saveData(); localStorage.setItem('vortex_daily', Date.now()); addHistory('Daily Login', DAILY_AMOUNT, 'Success'); alert(`+₦${DAILY_AMOUNT} Daily Login claimed!`); checkDailyStatus(); }

  function saveBank() {
    const bank = document.getElementById('bankName').value;
    const acc = document.getElementById('bankAcc').value;
    const holder = document.getElementById('bankHolder').value;
    if(!bank ||!acc ||!holder) return alert('Fill all bank fields');
    localStorage.setItem('vortex_bank', bank);
    localStorage.setItem('vortex_acc', acc);
    localStorage.setItem('vortex_holder', holder);
    updateBankText();
    alert('Bank details saved!');
  }
  function updateBankText() {
    const bank = localStorage.getItem('vortex_bank');
    const acc = localStorage.getItem('vortex_acc');
    const holder = localStorage.getItem('vortex_holder');
    if(bank && acc && holder) { document.getElementById('bankSavedText').textContent = `Saved: ${bank} - ${acc} - ${holder}`; withdrawToAccount.textContent = `Withdrawal to: ${bank} ${acc}`; }
    else { document.getElementById('bankSavedText').textContent = 'No bank saved yet'; withdrawToAccount.textContent = 'Add bank details above first'; }
  }
  function copyRef() { navigator.clipboard.writeText(refLink.value); alert('Referral link copied: ' + refLink.value); }
  function fakeRefCredit() { refBalance += 1000; saveData(); addHistory('Referral Credit', 1000, 'Success'); alert('+₦1,000 Referral Credit added!'); }

  // Withdraw preset buttons
  document.querySelectorAll('.withdraw-preset-btn').forEach(btn => {
    btn.addEventListener('click', function() {
      document.querySelectorAll('.withdraw-preset-btn').forEach(b => b.classList.remove('active'));
      this.classList.add('active');
      const amount = this.dataset.amount;
      if (amount === 'max') {
        withdrawAmount.value = balance;
      } else {
        withdrawAmount.value = amount;
      }
      updateWithdrawCalc();
    });
  });

  function updateWithdrawCalc() {
    const amt = parseInt(withdrawAmount.value) || 0;
    const charge = Math.round(amt * WITHDRAW_CHARGE);
    const net = amt - charge;
    withdrawCharge.textContent = '₦' + charge.toLocaleString();
    withdrawNet.textContent = '₦' + (net > 0? net.toLocaleString() : '0');
  }

  withdrawAmount.addEventListener('input', updateWithdrawCalc);

  function switchTab(tab) {
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.querySelectorAll('.auth-form').forEach(f => f.classList.remove('active'));
    if(tab === 'register') { document.querySelector('.tab-btns button:nth-child(1)').classList.add('active'); document.getElementById('registerForm').classList.add('active'); }
    else { document.querySelector('.tab-btns button:nth-child(2)').classList.add('active'); document.getElementById('loginForm').classList.add('active'); }
  }
  function enterApp(name) {
    if(name) { userName = name; localStorage.setItem('vortex_name', userName); }
    authSection.classList.add('hidden'); dashboard.classList.remove('hidden'); bottomNav.classList.remove('hidden'); loadData(); showPage('home');
  }
  function logout() {
    localStorage.clear(); balance = 200; refBalance = 0; userName = 'Guest'; history = [];
    dashboard.classList.add('hidden'); bottomNav.classList.add('hidden'); authSection.classList.remove('hidden');
    document.getElementById('accountBox').style.display = 'none'; withdrawAmount.value = ''; withdrawCharge.textContent = '₦0'; withdrawNet.textContent = '₦0';
  }
  document.getElementById('registerForm').addEventListener('submit', e => { e.preventDefault(); const name = document.getElementById('regName').value || 'User'; alert(`Registration successful! Welcome Bonus ₦200 credited.`); enterApp(name); addHistory('Welcome Bonus', 200, 'Success'); });
  document.getElementById('loginForm').addEventListener('submit', e => { e.preventDefault(); alert('Login successful!'); enterApp(); });

  const buttons = document.querySelectorAll('.amount-btn');
  const accountBox = document.getElementById('accountBox');
  const selectedAmount = document.getElementById('selectedAmount');
  const whatsappLink = document.getElementById('whatsappLink');
  const telegramLink = document.getElementById('telegramLink');
  buttons.forEach(btn => { btn.addEventListener('click', () => { buttons.forEach(b => b.classList.remove('active')); btn.classList.add('active'); selectedAmt = '₦' + btn.dataset.amount; selectedAmount.textContent = selectedAmt; accountBox.style.display = 'block'; accountBox.scrollIntoView({ behavior: 'smooth' }); updateSupportLinks(); }); });
  
  // Deposit - Only submit proof, no money added
  document.getElementById('confirmRechargeBtn').addEventListener('click', () => {
    if(selectedAmt === "₦0") return alert('Select an amount first');
    const file = document.getElementById('proofUpload').files[0];
    if(!file) return alert('Please upload proof of payment first');
    
    const amtNum = parseInt(selectedAmt.replace(/[^0-9]/g,''));
    addHistory('Deposit Request', amtNum, 'Pending');
    alert(`✅ Deposit request submitted!\nAmount: ₦${amtNum.toLocaleString()}\nStatus: Pending Approval\n\nYour account will be credited after approval.`);
    
    // Reset
    document.getElementById('proofUpload').value = '';
    document.getElementById('fileName').textContent = '';
    uploadedFile = '';
    accountBox.style.display = 'none';
    buttons.forEach(b => b.classList.remove('active'));
    selectedAmt = "₦0";
  });

  // WITHDRAW LOGIC
  document.getElementById('withdrawBtn').addEventListener('click', () => {
    const amt = parseInt(withdrawAmount.value);
    const now = new Date();
    const hour = now.getHours() + now.getMinutes()/60;
    const bank = localStorage.getItem('vortex_bank');
    const acc = localStorage.getItem('vortex_acc');
    const holder = localStorage.getItem('vortex_holder');

    if(!bank ||!acc ||!holder) return alert('Add your bank account details first');
    if(!amt || amt < MIN_WITHDRAW) return alert(`Minimum withdrawal is ₦${MIN_WITHDRAW}`);
    if(amt > balance) return alert(`Insufficient balance. Max: ₦${balance.toLocaleString()}`);
    if(hour < 7 || hour >= 19.5) return alert('Withdrawal time is 7:00am to 7:30pm only');

    balance -= amt;
    saveData();
    addHistory('Withdrawal', amt, 'Pending');
    alert(`Withdrawal Requested: ₦${amt.toLocaleString()}\nTo: ${bank} ${acc}\nCharge 17%: ₦${Math.round(amt*WITHDRAW_CHARGE).toLocaleString()}\nNew Balance: ₦${balance.toLocaleString()}`);
    withdrawAmount.value = '';
    withdrawCharge.textContent = '₦0';
    withdrawNet.textContent = '₦0';
    document.querySelectorAll('.withdraw-preset-btn').forEach(b => b.classList.remove('active'));
  });

  function copyText(id) { const text = document.getElementById(id).innerText; navigator.clipboard.writeText(text); alert('Account number copied: ' + text); }
  function updateSupportLinks() {
    const file = document.getElementById('proofUpload').files[0];
    if (file) { uploadedFile = file.name; document.getElementById('fileName').textContent = 'Selected: ' + uploadedFile + ' ✅'; }
    let message = `Hello Vortex Support,\n`;
    if (selectedAmt!== "₦0") { message += `I just paid ${selectedAmt} for recharge.\n`; }
    if (uploadedFile) { message += `File: ${uploadedFile}\n`; message += `Kindly confirm my payment.`; } else { message += `Kindly confirm my payment.`; }
    const encodedMsg = encodeURIComponent(message);
    whatsappLink.href = `https://wa.me/2349061933712?text=${encodedMsg}`;
    telegramLink.href = `https://t.me/mr_realfake247?text=${encodedMsg}`;
  }

  if(localStorage.getItem('vortex_balance')) { enterApp(); }
</script>
</body>
</html>
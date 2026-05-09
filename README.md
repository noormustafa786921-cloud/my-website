<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Brand Fusion - Together We Grow</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Rajdhani:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
<style>
:root {
  --bg-primary: #050d1a;
  --bg-secondary: #0a1628;
  --bg-card: #0d1f3c;
  --bg-card2: #071020;
  --accent-blue: #1565ff;
  --accent-cyan: #00d4ff;
  --accent-green: #00e676;
  --accent-orange: #ff6d00;
  --accent-purple: #7c3aed;
  --text-primary: #e8f4ff;
  --text-secondary: #7a9ec0;
  --border: #1a3a5c;
  --sidebar-w: 220px;
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:'Rajdhani',sans-serif; background:var(--bg-primary); color:var(--text-primary); min-height:100vh; overflow-x:hidden; }

/* ===== PAGES ===== */
.page { display:none; min-height:100vh; }
.page.active { display:block; }

/* ===== AUTH PAGES ===== */
.auth-wrap {
  min-height:100vh;
  display:flex;
  background: linear-gradient(135deg, #050d1a 0%, #0a1628 50%, #071020 100%);
  position:relative;
  overflow:hidden;
}
.auth-wrap::before {
  content:'';
  position:absolute;
  width:600px; height:600px;
  background: radial-gradient(circle, rgba(21,101,255,0.15) 0%, transparent 70%);
  top:-200px; right:-100px;
  border-radius:50%;
}
.auth-wrap::after {
  content:'';
  position:absolute;
  width:400px; height:400px;
  background: radial-gradient(circle, rgba(0,212,255,0.08) 0%, transparent 70%);
  bottom:-100px; left:-50px;
  border-radius:50%;
}
.auth-left {
  flex:1;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:40px;
  position:relative;
  z-index:2;
}
.auth-right {
  flex:1;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  padding:40px;
  background: rgba(13,31,60,0.5);
  backdrop-filter:blur(10px);
  position:relative;
  z-index:2;
}
.auth-illustration {
  text-align:center;
}
.auth-illustration h1 {
  font-family:'Orbitron',sans-serif;
  font-size:2.8rem;
  color:var(--accent-cyan);
  margin-bottom:10px;
  text-shadow:0 0 30px rgba(0,212,255,0.5);
}
.auth-illustration p {
  color:var(--text-secondary);
  font-size:1.1rem;
  margin-bottom:30px;
}
.auth-steps {
  display:flex;
  flex-direction:column;
  gap:16px;
  margin-top:30px;
}
.auth-step {
  display:flex;
  align-items:center;
  gap:14px;
  background: rgba(21,101,255,0.1);
  border:1px solid rgba(21,101,255,0.2);
  border-radius:12px;
  padding:14px 20px;
}
.step-icon {
  width:40px; height:40px;
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  border-radius:10px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:1.1rem;
  flex-shrink:0;
}
.step-text h4 { font-size:1rem; color:var(--text-primary); }
.step-text p { font-size:0.85rem; color:var(--text-secondary); }

.brand-logo {
  display:flex;
  align-items:center;
  gap:10px;
  margin-bottom:30px;
}
.logo-icon {
  width:48px; height:48px;
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  border-radius:12px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:1.4rem;
}
.brand-name h2 {
  font-family:'Orbitron',sans-serif;
  font-size:1.3rem;
  color:var(--text-primary);
  line-height:1;
}
.brand-name span {
  font-size:0.7rem;
  color:var(--text-secondary);
  display:block;
}

.auth-card {
  background: rgba(10,22,40,0.8);
  border:1px solid var(--border);
  border-radius:20px;
  padding:36px;
  width:100%;
  max-width:400px;
  backdrop-filter:blur(20px);
}
.auth-card h3 {
  font-family:'Orbitron',sans-serif;
  font-size:1.4rem;
  margin-bottom:6px;
  color:var(--accent-cyan);
}
.auth-card p.sub { color:var(--text-secondary); font-size:0.9rem; margin-bottom:24px; }

.form-group { margin-bottom:16px; }
.input-wrap {
  position:relative;
}
.input-wrap i {
  position:absolute;
  left:14px; top:50%;
  transform:translateY(-50%);
  color:var(--text-secondary);
  font-size:0.95rem;
}
.input-wrap input {
  width:100%;
  background: rgba(13,31,60,0.8);
  border:1px solid var(--border);
  border-radius:10px;
  padding:13px 14px 13px 40px;
  color:var(--text-primary);
  font-family:'Rajdhani',sans-serif;
  font-size:1rem;
  transition:border-color 0.2s;
}
.input-wrap input:focus {
  outline:none;
  border-color:var(--accent-blue);
  background: rgba(21,101,255,0.05);
}
.input-wrap input::placeholder { color:var(--text-secondary); }
.eye-toggle {
  position:absolute;
  right:14px; top:50%;
  transform:translateY(-50%);
  color:var(--text-secondary);
  cursor:pointer;
  font-size:0.9rem;
}

.checkbox-row {
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:20px;
  font-size:0.9rem;
}
.checkbox-row label { display:flex; align-items:center; gap:8px; cursor:pointer; color:var(--text-secondary); }
.checkbox-row a { color:var(--accent-cyan); text-decoration:none; }

.btn-primary {
  width:100%;
  padding:14px;
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  border:none;
  border-radius:10px;
  color:#fff;
  font-family:'Orbitron',sans-serif;
  font-size:0.95rem;
  font-weight:600;
  cursor:pointer;
  transition:all 0.2s;
  letter-spacing:1px;
}
.btn-primary:hover {
  transform:translateY(-2px);
  box-shadow:0 8px 25px rgba(21,101,255,0.4);
}
.auth-switch {
  text-align:center;
  margin-top:20px;
  color:var(--text-secondary);
  font-size:0.9rem;
}
.auth-switch a { color:var(--accent-cyan); text-decoration:none; font-weight:600; cursor:pointer; }

/* ===== PLAN PAGE ===== */
.plan-page {
  min-height:100vh;
  background: linear-gradient(135deg, #050d1a, #0a1628);
  padding:40px 20px;
}
.plan-header {
  text-align:center;
  margin-bottom:40px;
}
.plan-header h2 {
  font-family:'Orbitron',sans-serif;
  font-size:2rem;
  color:var(--accent-cyan);
  margin-bottom:8px;
}
.plan-header p { color:var(--text-secondary); }
.plans-grid {
  display:flex;
  gap:20px;
  justify-content:center;
  flex-wrap:wrap;
  max-width:900px;
  margin:0 auto;
}
.plan-card {
  background: var(--bg-card);
  border:1px solid var(--border);
  border-radius:20px;
  padding:30px;
  width:250px;
  text-align:center;
  transition:all 0.3s;
  position:relative;
  overflow:hidden;
}
.plan-card.popular {
  border-color:var(--accent-cyan);
  box-shadow:0 0 30px rgba(0,212,255,0.15);
}
.plan-card.popular::before {
  content:'POPULAR';
  position:absolute;
  top:14px; right:-24px;
  background:var(--accent-cyan);
  color:#050d1a;
  font-size:0.65rem;
  font-weight:700;
  padding:4px 30px;
  transform:rotate(45deg);
  letter-spacing:1px;
}
.plan-card:hover {
  transform:translateY(-6px);
  box-shadow:0 15px 40px rgba(21,101,255,0.2);
}
.plan-icon {
  font-size:2.5rem;
  margin-bottom:16px;
}
.plan-name {
  font-family:'Orbitron',sans-serif;
  font-size:1rem;
  color:var(--accent-cyan);
  margin-bottom:10px;
}
.plan-price {
  font-size:2.2rem;
  font-weight:700;
  color:var(--text-primary);
  margin-bottom:4px;
}
.plan-price span { font-size:1rem; }
.plan-period { color:var(--text-secondary); font-size:0.85rem; margin-bottom:20px; }
.plan-features {
  list-style:none;
  text-align:left;
  margin-bottom:24px;
}
.plan-features li {
  padding:6px 0;
  font-size:0.9rem;
  color:var(--text-secondary);
  border-bottom:1px solid rgba(26,58,92,0.3);
}
.plan-features li i { color:var(--accent-green); margin-right:8px; }
.btn-plan {
  width:100%;
  padding:12px;
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  border:none;
  border-radius:10px;
  color:#fff;
  font-family:'Orbitron',sans-serif;
  font-size:0.8rem;
  font-weight:600;
  cursor:pointer;
  transition:all 0.2s;
}
.btn-plan:hover { transform:translateY(-2px); box-shadow:0 6px 20px rgba(21,101,255,0.4); }

/* ===== DASHBOARD LAYOUT ===== */
.dashboard-layout { display:flex; min-height:100vh; }

/* Sidebar */
.sidebar {
  width:var(--sidebar-w);
  background: var(--bg-card2);
  border-right:1px solid var(--border);
  display:flex;
  flex-direction:column;
  position:fixed;
  top:0; left:0;
  height:100vh;
  z-index:100;
  overflow-y:auto;
}
.sidebar-brand {
  padding:20px 16px;
  border-bottom:1px solid var(--border);
  display:flex;
  align-items:center;
  gap:10px;
}
.sidebar-brand .logo-icon { width:38px; height:38px; font-size:1.1rem; }
.sidebar-brand .brand-name h2 { font-size:1rem; }
.sidebar-nav { flex:1; padding:16px 0; }
.nav-item {
  display:flex;
  align-items:center;
  gap:12px;
  padding:12px 20px;
  color:var(--text-secondary);
  cursor:pointer;
  transition:all 0.2s;
  font-size:0.95rem;
  font-weight:500;
  border-left:3px solid transparent;
}
.nav-item:hover { color:var(--text-primary); background:rgba(21,101,255,0.08); }
.nav-item.active {
  color:var(--text-primary);
  background: rgba(21,101,255,0.15);
  border-left-color:var(--accent-blue);
}
.nav-item i { width:18px; text-align:center; font-size:0.9rem; }
.sidebar-support {
  margin:10px 14px 20px;
  background: rgba(21,101,255,0.08);
  border:1px solid rgba(21,101,255,0.2);
  border-radius:12px;
  padding:14px;
  font-size:0.85rem;
}
.sidebar-support .support-title { color:var(--accent-cyan); font-weight:600; margin-bottom:4px; }
.sidebar-support .support-num { color:var(--text-secondary); }
.sidebar-support .support-num a { color:var(--accent-green); text-decoration:none; }

/* Main Content */
.main-content {
  margin-left:var(--sidebar-w);
  flex:1;
  display:flex;
  flex-direction:column;
}
.topbar {
  background: var(--bg-card2);
  border-bottom:1px solid var(--border);
  padding:14px 28px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  position:sticky;
  top:0;
  z-index:90;
}
.topbar-title { font-family:'Orbitron',sans-serif; font-size:1rem; color:var(--accent-cyan); }
.topbar-right { display:flex; align-items:center; gap:16px; }
.notif-btn {
  width:36px; height:36px;
  background: rgba(21,101,255,0.1);
  border:1px solid var(--border);
  border-radius:10px;
  display:flex;
  align-items:center;
  justify-content:center;
  cursor:pointer;
  position:relative;
  color:var(--text-secondary);
}
.notif-dot {
  position:absolute;
  top:5px; right:5px;
  width:8px; height:8px;
  background:var(--accent-orange);
  border-radius:50%;
}
.user-chip {
  display:flex;
  align-items:center;
  gap:10px;
  background: rgba(13,31,60,0.8);
  border:1px solid var(--border);
  border-radius:10px;
  padding:6px 12px;
  cursor:pointer;
}
.user-avatar {
  width:30px; height:30px;
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  border-radius:8px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:0.85rem;
}
.user-info { line-height:1.2; }
.user-info .u-name { font-size:0.9rem; color:var(--text-primary); }
.user-info .u-id { font-size:0.75rem; color:var(--text-secondary); }

/* Dashboard Content */
.dash-content { padding:24px 28px; }
.breadcrumb { font-size:0.85rem; color:var(--text-secondary); margin-bottom:20px; }
.breadcrumb span { color:var(--accent-cyan); }

/* Balance Card */
.balance-card {
  background: linear-gradient(135deg, #0a1f4a 0%, #0d2d6a 50%, #0a1f4a 100%);
  border:1px solid rgba(21,101,255,0.3);
  border-radius:20px;
  padding:28px;
  margin-bottom:20px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  position:relative;
  overflow:hidden;
}
.balance-card::before {
  content:'';
  position:absolute;
  top:-60px; right:-60px;
  width:200px; height:200px;
  background: radial-gradient(circle, rgba(0,212,255,0.1) 0%, transparent 70%);
  border-radius:50%;
}
.balance-left h4 { color:var(--text-secondary); font-size:0.85rem; letter-spacing:2px; text-transform:uppercase; margin-bottom:8px; }
.balance-amount {
  font-family:'Orbitron',sans-serif;
  font-size:2.4rem;
  font-weight:700;
  color:var(--text-primary);
  margin-bottom:6px;
}
.balance-amount.zero { color:var(--text-secondary); font-size:1.8rem; }
.balance-earning { color:var(--text-secondary); font-size:0.9rem; }
.balance-earning strong { color:var(--accent-green); }
.balance-actions { display:flex; gap:12px; margin-top:20px; }
.btn-action {
  padding:10px 24px;
  border-radius:10px;
  font-family:'Rajdhani',sans-serif;
  font-size:0.95rem;
  font-weight:600;
  cursor:pointer;
  transition:all 0.2s;
  border:none;
}
.btn-add {
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  color:#fff;
}
.btn-withdraw {
  background: transparent;
  border:1px solid var(--border);
  color:var(--text-secondary);
}
.btn-withdraw:hover { border-color:var(--accent-blue); color:var(--text-primary); }
.balance-icon { font-size:4rem; opacity:0.4; }

/* Stats */
.stats-grid {
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:16px;
  margin-bottom:20px;
}
.stat-card {
  background: var(--bg-card);
  border:1px solid var(--border);
  border-radius:16px;
  padding:20px;
  display:flex;
  align-items:center;
  gap:14px;
}
.stat-icon {
  width:50px; height:50px;
  border-radius:14px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:1.3rem;
  flex-shrink:0;
}
.stat-icon.purple { background:rgba(124,58,237,0.2); color:#a78bfa; }
.stat-icon.green { background:rgba(0,230,118,0.15); color:var(--accent-green); }
.stat-icon.orange { background:rgba(255,109,0,0.15); color:var(--accent-orange); }
.stat-icon.cyan { background:rgba(0,212,255,0.12); color:var(--accent-cyan); }
.stat-info h4 { color:var(--text-secondary); font-size:0.8rem; margin-bottom:4px; text-transform:uppercase; letter-spacing:1px; }
.stat-value { font-size:1.5rem; font-weight:700; color:var(--text-primary); }
.stat-link { font-size:0.78rem; color:var(--accent-cyan); cursor:pointer; margin-top:4px; }

/* Two-col grid */
.two-col { display:grid; grid-template-columns:1fr 1fr; gap:20px; margin-bottom:20px; }
.section-card {
  background: var(--bg-card);
  border:1px solid var(--border);
  border-radius:16px;
  padding:20px;
}
.section-header {
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:16px;
}
.section-header h3 { font-size:1rem; font-weight:600; color:var(--text-primary); letter-spacing:1px; }
.section-header select {
  background: var(--bg-card2);
  border:1px solid var(--border);
  border-radius:8px;
  padding:5px 10px;
  color:var(--text-secondary);
  font-size:0.85rem;
}

/* Referral */
.referral-card {
  background: var(--bg-card);
  border:1px solid var(--border);
  border-radius:16px;
  padding:20px;
  margin-bottom:20px;
}
.referral-card h3 { font-size:0.9rem; letter-spacing:2px; text-transform:uppercase; color:var(--text-secondary); margin-bottom:14px; }
.ref-link-wrap {
  display:flex;
  gap:10px;
  margin-bottom:16px;
}
.ref-link-input {
  flex:1;
  background: var(--bg-card2);
  border:1px solid var(--border);
  border-radius:10px;
  padding:11px 14px;
  color:var(--accent-cyan);
  font-size:0.85rem;
}
.ref-copy-btn {
  padding:11px 16px;
  background: rgba(21,101,255,0.15);
  border:1px solid rgba(21,101,255,0.3);
  border-radius:10px;
  color:var(--accent-cyan);
  cursor:pointer;
  transition:all 0.2s;
}
.ref-copy-btn:hover { background:rgba(21,101,255,0.25); }
.share-label { color:var(--text-secondary); font-size:0.85rem; margin-bottom:10px; }
.share-btns { display:flex; gap:10px; }
.share-btn {
  width:40px; height:40px;
  border-radius:10px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:1.1rem;
  cursor:pointer;
  transition:all 0.2s;
}
.share-btn:hover { transform:scale(1.1); }
.sb-wa { background:rgba(37,211,102,0.15); color:#25d366; border:1px solid rgba(37,211,102,0.2); }
.sb-tg { background:rgba(0,136,204,0.15); color:#0088cc; border:1px solid rgba(0,136,204,0.2); }
.sb-fb { background:rgba(24,119,242,0.15); color:#1877f2; border:1px solid rgba(24,119,242,0.2); }
.sb-tw { background:rgba(29,161,242,0.15); color:#1da1f2; border:1px solid rgba(29,161,242,0.2); }
.sb-share { background:rgba(255,255,255,0.06); color:var(--text-secondary); border:1px solid var(--border); }

/* Tree */
.tree-wrap { display:flex; flex-direction:column; align-items:center; gap:0; }
.tree-node {
  display:flex;
  flex-direction:column;
  align-items:center;
}
.tree-self {
  background: linear-gradient(135deg,var(--accent-blue),var(--accent-cyan));
  border-radius:50%;
  width:48px; height:48px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:1.2rem;
  margin-bottom:4px;
}
.tree-name { font-size:0.78rem; color:var(--text-primary); }
.tree-team { font-size:0.7rem; color:var(--text-secondary); }
.tree-line {
  width:1px; height:30px;
  background: var(--border);
}
.tree-children {
  display:flex;
  gap:20px;
}
.tree-child {
  display:flex;
  flex-direction:column;
  align-items:center;
}
.tree-child-icon {
  width:42px; height:42px;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:1rem;
  margin-bottom:4px;
}
.tc-purple { background:rgba(124,58,237,0.2); color:#a78bfa; border:1px solid rgba(124,58,237,0.3); }
.tc-green { background:rgba(0,230,118,0.15); color:var(--accent-green); border:1px solid rgba(0,230,118,0.2); }
.tc-orange { background:rgba(255,109,0,0.15); color:var(--accent-orange); border:1px solid rgba(255,109,0,0.2); }
.tc-cyan { background:rgba(0,212,255,0.12); color:var(--accent-cyan); border:1px solid rgba(0,212,255,0.2); }
.tree-child-name { font-size:0.72rem; color:var(--text-secondary); }
.tree-child-num { font-size:0.75rem; color:var(--text-primary); font-weight:600; }
.view-team-btn {
  margin-top:14px;
  padding:8px 20px;
  background: rgba(21,101,255,0.1);
  border:1px solid rgba(21,101,255,0.25);
  border-radius:8px;
  color:var(--accent-cyan);
  font-size:0.85rem;
  cursor:pointer;
}

/* Chart */
.chart-area {
  height:160px;
  position:relative;
  overflow:hidden;
}
#incomeChart { width:100%; height:100%; }

/* Table */
.data-table { width:100%; border-collapse:collapse; font-size:0.88rem; }
.data-table th {
  padding:10px 12px;
  text-align:left;
  color:var(--text-secondary);
  font-size:0.78rem;
  text-transform:uppercase;
  letter-spacing:1px;
  border-bottom:1px solid var(--border);
}
.data-table td {
  padding:11px 12px;
  border-bottom:1px solid rgba(26,58,92,0.3);
  color:var(--text-primary);
}
.badge {
  padding:3px 10px;
  border-radius:20px;
  font-size:0.75rem;
  font-weight:600;
}
.badge-active { background:rgba(0,230,118,0.15); color:var(--accent-green); }
.badge-pending { background:rgba(255,109,0,0.15); color:var(--accent-orange); }
.badge-inactive { background:rgba(122,158,192,0.15); color:var(--text-secondary); }
.badge-completed { background:rgba(0,212,255,0.12); color:var(--accent-cyan); }
.badge-approved { background:rgba(0,230,118,0.15); color:var(--accent-green); }
.badge-rejected { background:rgba(255,50,50,0.15); color:#ff5252; }

.action-btns { display:flex; gap:6px; }
.btn-view {
  padding:4px 12px;
  background: rgba(21,101,255,0.15);
  border:1px solid rgba(21,101,255,0.25);
  border-radius:6px;
  color:var(--accent-cyan);
  font-size:0.78rem;
  cursor:pointer;
}
.btn-approve {
  padding:4px 12px;
  background: rgba(0,230,118,0.1);
  border:1px solid rgba(0,230,118,0.2);
  border-radius:6px;
  color:var(--accent-green);
  font-size:0.78rem;
  cursor:pointer;
}
.btn-reject {
  padding:4px 12px;
  background: rgba(255,50,50,0.1);
  border:1px solid rgba(255,50,50,0.2);
  border-radius:6px;
  color:#ff5252;
  font-size:0.78rem;
  cursor:pointer;
}

/* Search */
.search-bar {
  display:flex;
  align-items:center;
  gap:10px;
  background: var(--bg-card2);
  border:1px solid var(--border);
  border-radius:10px;
  padding:10px 14px;
  margin-bottom:16px;
}
.search-bar input {
  background:none;
  border:none;
  outline:none;
  color:var(--text-primary);
  font-family:'Rajdhani',sans-serif;
  

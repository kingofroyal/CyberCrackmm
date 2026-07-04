<!DOCTYPE html>
<html lang="ckb">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CyberCrack - پەڕەی خاوەن و ئەندام</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background: #0a0f1e;
            color: #c8d6e5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        .container {
            background: #141b2b;
            max-width: 1200px;
            width: 100%;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 0 40px rgba(0, 255, 200, 0.1);
            border: 1px solid #1f2b3f;
        }
        h1, h2, h3 {
            color: #00f5d4;
            text-shadow: 0 0 10px rgba(0, 245, 212, 0.3);
            letter-spacing: 1px;
        }
        .flex-row {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: space-between;
            align-items: center;
        }
        .card {
            background: #1a2438;
            border-radius: 12px;
            padding: 20px;
            margin-top: 20px;
            border-left: 4px solid #00f5d4;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }
        input, select, button {
            background: #0f172a;
            border: 1px solid #2a3a55;
            color: #e2e8f0;
            padding: 10px 16px;
            border-radius: 8px;
            font-size: 1rem;
            transition: 0.3s;
        }
        input:focus, select:focus {
            outline: none;
            border-color: #00f5d4;
            box-shadow: 0 0 15px rgba(0, 245, 212, 0.2);
        }
        button {
            background: #00f5d4;
            color: #0a0f1e;
            font-weight: bold;
            border: none;
            cursor: pointer;
            transition: 0.3s;
        }
        button:hover {
            background: #00ccb3;
            transform: scale(1.02);
            box-shadow: 0 0 20px rgba(0, 245, 212, 0.4);
        }
        .btn-danger {
            background: #ff4757;
            color: white;
        }
        .btn-danger:hover {
            background: #e8414f;
            box-shadow: 0 0 20px rgba(255, 71, 87, 0.4);
        }
        .btn-warning {
            background: #f39c12;
            color: #0a0f1e;
        }
        .btn-warning:hover {
            background: #e67e22;
        }
        .hidden {
            display: none !important;
        }
        .visitor-badge {
            background: #0f172a;
            padding: 8px 20px;
            border-radius: 30px;
            border: 1px solid #f0a500;
            color: #f0a500;
            font-weight: bold;
            font-size: 1.2rem;
        }
        .tab-bar {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin: 15px 0;
            border-bottom: 1px solid #2a3a55;
            padding-bottom: 10px;
        }
        .tab-btn {
            background: transparent;
            color: #8892b0;
            border: 1px solid transparent;
            padding: 8px 18px;
            cursor: pointer;
        }
        .tab-btn.active {
            background: #00f5d4;
            color: #0a0f1e;
            border-radius: 20px;
            border-color: #00f5d4;
        }
        .user-row {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: space-between;
            align-items: center;
            background: #0f172a;
            padding: 12px 15px;
            border-radius: 8px;
            margin-bottom: 8px;
            border-left: 3px solid #2a3a55;
        }
        .user-row .info {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            align-items: center;
        }
        .owner-tag {
            background: #f0a500;
            color: #0a0f1e;
            font-size: 0.7rem;
            padding: 2px 10px;
            border-radius: 20px;
            font-weight: bold;
        }
        .status-msg {
            color: #ff6b6b;
            margin-top: 10px;
            font-weight: bold;
        }
        .grid-2 {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        @media (max-width: 700px) {
            .grid-2 {
                grid-template-columns: 1fr;
            }
        }
        .crack-header {
            color: #f0a500;
            text-shadow: 0 0 20px rgba(240, 165, 0, 0.5);
        }
        .cat-item {
            background: #0f172a;
            padding: 10px 15px;
            border-radius: 8px;
            margin-bottom: 6px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-left: 3px solid #f0a500;
        }
    </style>
</head>
<body>
<div class="container" id="app">
    <header class="flex-row">
        <h1>💀 CyberCrack</h1>
        <div class="visitor-badge" id="visitorDisplay">👁️ بینەران: 0</div>
    </header>

    <!-- ========== VIEW: PUBLIC (pre-login) ========== -->
    <div id="view-public">
        <div class="card" style="border-color:#f0a500;">
            <p style="font-size:1.1rem;">بۆ چوونە ناو وێبسایتەکە، یان <strong>هەژمارێک دروست بکە</strong> یان <strong>بچیتە ژوورەوە</strong>.</p>
            <p style="color:#8892b0;">ئەم وێبسایتە پۆل/کاتێگۆری تایبەت بە خاوەنەکان هەیە، و ئەندامان دەتوانن لیستی خاوەنەکان ببینن.</p>
        </div>
        <div class="tab-bar">
            <button class="tab-btn active" data-tab="tab-user-login">چوونەژوورەوەی بەکارهێنەر</button>
            <button class="tab-btn" data-tab="tab-user-register">تۆمارکردن</button>
            <button class="tab-btn" data-tab="tab-owner-login" style="border:1px solid #f0a500; color:#f0a500;">🔑 چوونەژوورەوەی خاوەن</button>
        </div>
        <div id="tab-user-login" class="tab-content">
            <div class="card">
                <h3>👤 چوونەژوورەوەی بەکارهێنەر</h3>
                <div class="grid-2" style="margin-top:15px;">
                    <input type="text" id="login-username" placeholder="ناوی بەکارهێنەر">
                    <input type="password" id="login-password" placeholder="تێپەڕەوشە">
                </div>
                <button onclick="userLogin()">چوونەژوورەوە</button>
                <div id="login-status" class="status-msg"></div>
            </div>
        </div>
        <div id="tab-user-register" class="tab-content hidden">
            <div class="card">
                <h3>📝 تۆمارکردنی هەژمار</h3>
                <div class="grid-2" style="margin-top:15px;">
                    <input type="text" id="reg-username" placeholder="ناوی بەکارهێنەر">
                    <input type="password" id="reg-password" placeholder="تێپەڕەوشە">
                </div>
                <button onclick="userRegister()">تۆمارکردن</button>
                <div id="reg-status" class="status-msg"></div>
            </div>
        </div>
        <div id="tab-owner-login" class="tab-content hidden">
            <div class="card" style="border-color:#f0a500; background:#1f1a2e;">
                <h3>🔐 چوونەژوورەوەی خاوەن (Owner)</h3>
                <p style="color:#f0a500; font-size:0.9rem;">تەنها خاوەنەکان دەسترسیان بەم بەشە هەیە.</p>
                <div class="grid-2" style="margin-top:15px;">
                    <input type="text" id="owner-login-username" placeholder="ناوی بەکارهێنەر">
                    <input type="password" id="owner-login-password" placeholder="تێپەڕەوشە">
                </div>
                <button onclick="ownerLogin()" style="background:#f0a500; color:#0a0f1e;">چوونەژوورەوەی خاوەن</button>
                <div id="owner-login-status" class="status-msg"></div>
            </div>
        </div>
    </div>

    <!-- ========== VIEW: MEMBER DASHBOARD ========== -->
    <div id="view-member-dashboard" class="hidden">
        <div class="flex-row">
            <h2>👤 بەخێربێیت <span id="member-name"></span></h2>
            <button onclick="logout()" class="btn-danger">دەرچوون</button>
        </div>
        <div class="card" style="border-color:#2a3a55;">
            <p><strong>ناوی تۆ:</strong> <span id="member-username"></span></p>
            <p><strong>ئایپی تۆ:</strong> <span id="member-ip"></span></p>
        </div>
        <div class="card" style="border-color:#f0a500;">
            <h3 class="crack-header">👑 لیستی خاوەنەکان</h3>
            <div id="member-owners-list"></div>
        </div>
        <div class="card">
            <h3>📂 کاتێگۆری/پۆلەکان</h3>
            <div id="member-categories-list"></div>
        </div>
    </div>

    <!-- ========== VIEW: OWNER DASHBOARD ========== -->
    <div id="view-owner-dashboard" class="hidden">
        <div class="flex-row">
            <h2>👑 پەڕەی خاوەن <span style="font-size:0.8rem; color:#f0a500;">CyberCrack</span></h2>
            <button onclick="logout()" class="btn-danger">دەرچوون</button>
        </div>
        <div class="tab-bar">
            <button class="tab-btn active" data-owner-tab="owner-categories">📂 کاتێگۆری</button>
            <button class="tab-btn" data-owner-tab="owner-users">👥 بەکارهێنەران</button>
            <button class="tab-btn" data-owner-tab="owner-settings">⚙️ ڕێکخستنەکان</button>
        </div>
        <!-- Owner: Categories -->
        <div id="owner-categories" class="owner-tab-content">
            <div class="card" style="border-color:#f0a500;">
                <h3 class="crack-header">📂 بەڕێوەبردنی کاتێگۆری/پۆل</h3>
                <div class="flex-row" style="gap:10px; margin-bottom:15px;">
                    <input type="text" id="new-category-name" placeholder="ناوی کاتێگۆری نوێ" style="flex:1;">
                    <button onclick="addCategory()">زیادکردن</button>
                </div>
                <div id="owner-categories-list"></div>
            </div>
        </div>
        <!-- Owner: Users -->
        <div id="owner-users" class="owner-tab-content hidden">
            <div class="card">
                <h3>👥 بەکارهێنەران و ئایپییەکان</h3>
                <div id="owner-users-list"></div>
            </div>
        </div>
        <!-- Owner: Settings -->
        <div id="owner-settings" class="owner-tab-content hidden">
            <div class="card">
                <h3>⚙️ ڕێکخستنەکان</h3>
                <div style="margin:15px 0;">
                    <label>ژمێری بینەران:</label>
                    <div class="flex-row" style="gap:10px; margin-top:5px;">
                        <input type="number" id="editVisitorCount" style="width:150px;">
                        <button onclick="updateVisitorCount()">نوێکردنەوە</button>
                        <button onclick="adjustVisitor(1)" class="btn-warning">+1</button>
                        <button onclick="adjustVisitor(-1)" class="btn-warning">-1</button>
                    </div>
                </div>
                <hr style="border-color:#2a3a55; margin:20px 0;">
                <div>
                    <h4>👑 بەڕێوەبردنی خاوەنەکان</h4>
                    <div class="flex-row" style="gap:10px; margin-top:10px;">
                        <select id="ownerSelectUser" style="flex:1;"></select>
                        <button onclick="addOwner()">زیادکردنی خاوەن</button>
                    </div>
                    <div id="currentOwnersList" style="margin-top:15px;"></div>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
    // ============================================================
    //  Database
    // ============================================================
    function getUsers() {
        return JSON.parse(localStorage.getItem('cybercrack_users')) || [];
    }
    function saveUsers(users) {
        localStorage.setItem('cybercrack_users', JSON.stringify(users));
    }
    function getBans() {
        return JSON.parse(localStorage.getItem('cybercrack_bans')) || [];
    }
    function saveBans(bans) {
        localStorage.setItem('cybercrack_bans', JSON.stringify(bans));
    }
    function getCategories() {
        return JSON.parse(localStorage.getItem('cybercrack_categories')) || [];
    }
    function saveCategories(cats) {
        localStorage.setItem('cybercrack_categories', JSON.stringify(cats));
    }
    function getVisitorCount() {
        return parseInt(localStorage.getItem('cybercrack_visitor')) || 0;
    }
    function setVisitorCount(val) {
        localStorage.setItem('cybercrack_visitor', val);
        updateVisitorDisplay();
    }
    function getCurrentUser() {
        return JSON.parse(sessionStorage.getItem('cybercrack_current_user'));
    }
    function setCurrentUser(user) {
        sessionStorage.setItem('cybercrack_current_user', JSON.stringify(user));
    }
    function clearCurrentUser() {
        sessionStorage.removeItem('cybercrack_current_user');
    }

    // ============================================================
    //  IP Detection
    // ============================================================
    async function fetchIP() {
        try {
            const res = await fetch('https://api.ipify.org?format=json');
            const data = await res.json();
            return data.ip;
        } catch {
            return '0.0.0.0';
        }
    }

    // ============================================================
    //  Init
    // ============================================================
    async function init() {
        let users = getUsers();
        if (users.length === 0) {
            const defaultIP = await fetchIP();
            users = [{
                id: Date.now() + 1,
                username: 'admin',
                password: 'admin123',
                ip: defaultIP,
                isOwner: true
            }];
            saveUsers(users);
        }
        let visitors = getVisitorCount();
        if (!sessionStorage.getItem('cybercrack_visited')) {
            visitors += 1;
            setVisitorCount(visitors);
            sessionStorage.setItem('cybercrack_visited', 'true');
        } else {
            updateVisitorDisplay();
        }
        const current = getCurrentUser();
        if (current) {
            const user = users.find(u => u.id === current.id && u.username === current.username);
            if (user) {
                if (getBans().includes(user.ip)) {
                    clearCurrentUser();
                    alert('ئایپی تۆ باند کراوە! ناتوانیت بچیتە ژوورەوە.');
                    showPublicView();
                    return;
                }
                if (user.isOwner) {
                    showOwnerDashboard(user);
                } else {
                    showMemberDashboard(user);
                }
                return;
            } else {
                clearCurrentUser();
            }
        }
        showPublicView();
    }

    // ============================================================
    //  View Controllers
    // ============================================================
    function hideAll() {
        document.getElementById('view-public').classList.add('hidden');
        document.getElementById('view-member-dashboard').classList.add('hidden');
        document.getElementById('view-owner-dashboard').classList.add('hidden');
    }

    function showPublicView() {
        hideAll();
        document.getElementById('view-public').classList.remove('hidden');
        document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
        document.querySelectorAll('.tab-btn[data-tab]').forEach(b => b.classList.remove('active'));
        document.querySelector('[data-tab="tab-user-login"]').classList.add('active');
        document.getElementById('tab-user-login').classList.remove('hidden');
        updateVisitorDisplay();
    }

    function showMemberDashboard(user) {
        hideAll();
        document.getElementById('view-member-dashboard').classList.remove('hidden');
        document.getElementById('member-name').innerText = user.username;
        document.getElementById('member-username').innerText = user.username;
        document.getElementById('member-ip').innerText = user.ip;
        renderMemberOwners();
        renderMemberCategories();
    }

    function showOwnerDashboard(user) {
        hideAll();
        document.getElementById('view-owner-dashboard').classList.remove('hidden');
        document.querySelectorAll('.owner-tab-content').forEach(el => el.classList.add('hidden'));
        document.querySelectorAll('[data-owner-tab]').forEach(b => b.classList.remove('active'));
        document.querySelector('[data-owner-tab="owner-categories"]').classList.add('active');
        document.getElementById('owner-categories').classList.remove('hidden');
        refreshOwnerUI();
    }

    function updateVisitorDisplay() {
        document.getElementById('visitorDisplay').innerText = '👁️ بینەران: ' + getVisitorCount();
    }

    // ============================================================
    //  Tab Switching (Public)
    // ============================================================
    document.querySelectorAll('[data-tab]').forEach(btn => {
        btn.addEventListener('click', function() {
            document.querySelectorAll('.tab-btn[data-tab]').forEach(b => b.classList.remove('active'));
            this.classList.add('active');
            const target = this.getAttribute('data-tab');
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(target).classList.remove('hidden');
            document.getElementById('login-status').innerText = '';
            document.getElementById('reg-status').innerText = '';
            document.getElementById('owner-login-status').innerText = '';
        });
    });

    // Owner Tabs
    document.querySelectorAll('[data-owner-tab]').forEach(btn => {
        btn.addEventListener('click', function() {
            document.querySelectorAll('[data-owner-tab]').forEach(b => b.classList.remove('active'));
            this.classList.add('active');
            const target = this.getAttribute('data-owner-tab');
            document.querySelectorAll('.owner-tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(target).classList.remove('hidden');
            if (target === 'owner-users') renderOwnerUsers();
            if (target === 'owner-settings') refreshSettings();
            if (target === 'owner-categories') renderOwnerCategories();
        });
    });

    // ============================================================
    //  Authentication
    // ============================================================
    async function userRegister() {
        const username = document.getElementById('reg-username').value.trim();
        const password = document.getElementById('reg-password').value.trim();
        const status = document.getElementById('reg-status');
        if (!username || !password) { status.innerText = 'تکایە هەموو خانەکان پڕ بکەوە.'; return; }
        const users = getUsers();
        if (users.find(u => u.username === username)) { status.innerText = 'ئەم ناوە هەیە.'; return; }
        const ip = await fetchIP();
        const newUser = { id: Date.now(), username, password, ip, isOwner: false };
        users.push(newUser);
        saveUsers(users);
        status.innerText = '✅ هەژمارت دروست بوو! ئێستا بچۆ ژوورەوە.';
        document.getElementById('reg-username').value = '';
        document.getElementById('reg-password').value = '';
    }

    async function userLogin() {
        const username = document.getElementById('login-username').value.trim();
        co

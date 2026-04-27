<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>PK Tank Tracking</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- HTML5 QR Code -->
    <script src="https://unpkg.com/html5-qrcode" type="text/javascript"></script>
    <!-- SweetAlert2 -->
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <!-- SheetJS (สำหรับ Export Excel) -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    
    <!-- Libraries สำหรับสร้าง PDF Label -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    
    <style>
        body { font-family: 'Sarabun', sans-serif; background-color: #f3f4f6; margin: 0; padding: 0; overflow: hidden; }
        .tab-content { display: none; }
        .tab-content.active { display: block; }
        #reader { width: 100%; max-width: 500px; margin: 0 auto; border-radius: 1rem; overflow: hidden; background-color: #000; min-height: 250px; border: 4px solid #fff; box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1); }
        .scan-region-highlight { border-radius: 10px !important; border: 2px solid #3b82f6 !important; }
        
        /* Custom scrollbar for desktop */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
        ::-webkit-scrollbar-thumb:hover { background: #94a3b8; }
    </style>
</head>
<body>

    <!-- Login Screen -->
    <div id="login-screen" class="fixed inset-0 bg-blue-800 flex items-center justify-center z-[100] px-4">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-sm p-8 text-center transform transition-all">
            <img src="https://lh3.googleusercontent.com/d/1s93jOMu2iYhmBbcNAiMc0cNYDzsQ2izQ" alt="PK Tank Logo" class="h-28 mx-auto mb-4 object-contain">
            <h2 class="text-2xl font-black text-gray-800 mb-1">เข้าสู่ระบบ</h2>
            <p class="text-sm text-gray-500 mb-8 font-bold">PK Tank Tracking System</p>
            
            <div class="space-y-4 mb-8 text-left">
                <div>
                    <label class="block text-xs font-bold text-gray-500 mb-1 pl-1">ชื่อผู้ใช้งาน (Username)</label>
                    <input type="text" id="login-user" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-blue-50 text-sm font-bold uppercase transition-colors" placeholder="ระบุชื่อผู้ใช้">
                </div>
                <div>
                    <label class="block text-xs font-bold text-gray-500 mb-1 pl-1">รหัสผ่าน (Password)</label>
                    <div class="relative">
                        <input type="password" id="login-pass" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-blue-50 text-sm font-bold transition-colors pr-10" placeholder="ระบุรหัสผ่าน" onkeypress="if(event.key === 'Enter') handleLogin()">
                        <button type="button" onclick="togglePasswordVisibility()" class="absolute inset-y-0 right-0 pr-3 flex items-center text-gray-400 hover:text-gray-600 focus:outline-none">
                            <i id="toggle-pass-icon" class="fa-solid fa-eye text-lg"></i>
                        </button>
                    </div>
                </div>
            </div>
            
            <button onclick="handleLogin()" class="w-full bg-blue-600 text-white font-bold py-4 rounded-xl shadow-lg hover:bg-blue-700 transition-transform active:scale-95 mb-4 text-sm">เข้าสู่ระบบ</button>
            <div class="text-xs text-gray-400 font-bold">สำหรับใช้งานภายในองค์กรเท่านั้น</div>
        </div>
    </div>

    <!-- App Wrapper (Responsive Flex Layout) - Hidden by default -->
    <div id="app-wrapper" style="display: none;" class="flex h-screen w-full bg-gray-50">

        <!-- 1. LEFT SIDEBAR (DESKTOP & TABLET ONLY) -->
        <aside class="hidden md:flex flex-col w-64 bg-white border-r border-gray-200 shadow-sm z-20 shrink-0">
            <!-- Logo -->
            <div class="h-16 flex items-center justify-between px-6 bg-blue-800 text-white shadow-sm">
                <h1 class="text-xl font-bold tracking-wider flex items-center">
                    <img src="https://lh3.googleusercontent.com/d/1s93jOMu2iYhmBbcNAiMc0cNYDzsQ2izQ" alt="PK Tank" class="h-8 w-auto mr-2 object-contain">
                    PK Tank
                </h1>
            </div>
            
            <!-- Navigation Links -->
            <nav class="flex-1 py-6 px-4 space-y-2 overflow-y-auto">
                <button onclick="switchTab('dashboard')" id="nav-desktop-dashboard" class="nav-btn-desktop w-full flex items-center px-4 py-3 text-blue-600 bg-blue-50 rounded-xl font-bold transition-all text-left">
                    <i class="fa-solid fa-chart-pie w-6 text-lg text-center"></i> <span class="ml-2 text-sm">แดชบอร์ด</span>
                </button>
                <button onclick="switchTab('stock')" id="nav-desktop-stock" class="nav-btn-desktop w-full flex items-center px-4 py-3 text-gray-500 hover:bg-gray-50 rounded-xl font-bold transition-all text-left">
                    <i class="fa-solid fa-layer-group w-6 text-lg text-center"></i> <span class="ml-2 text-sm">สต็อกถัง</span>
                </button>
                <button onclick="switchTab('scan')" id="nav-desktop-scan" class="nav-btn-desktop w-full flex items-center px-4 py-3 text-gray-500 hover:bg-gray-50 rounded-xl font-bold transition-all text-left">
                    <i class="fa-solid fa-qrcode w-6 text-lg text-center"></i> <span class="ml-2 text-sm">สแกนถัง / บันทึก</span>
                </button>
                <button onclick="switchTab('manage')" id="nav-desktop-manage" class="nav-btn-desktop w-full flex items-center px-4 py-3 text-gray-500 hover:bg-gray-50 rounded-xl font-bold transition-all text-left">
                    <i class="fa-solid fa-gear w-6 text-lg text-center"></i> <span class="ml-2 text-sm">จัดการถัง</span>
                </button>
                <button onclick="switchTab('label')" id="nav-desktop-label" class="nav-btn-desktop w-full flex items-center px-4 py-3 text-gray-500 hover:bg-gray-50 rounded-xl font-bold transition-all text-left">
                    <i class="fa-solid fa-tags w-6 text-lg text-center"></i> <span class="ml-2 text-sm">สร้างเลเบลถัง</span>
                </button>
                <button onclick="switchTab('search')" id="nav-desktop-search" class="nav-btn-desktop w-full flex items-center px-4 py-3 text-gray-500 hover:bg-gray-50 rounded-xl font-bold transition-all text-left">
                    <i class="fa-solid fa-magnifying-glass w-6 text-lg text-center"></i> <span class="ml-2 text-sm">ค้นหาและประวัติ</span>
                </button>
            </nav>
            
            <!-- Status Footer & Logout -->
            <div class="p-4 border-t border-gray-100 flex flex-col gap-2">
                <div class="bg-gray-50 rounded-xl p-3 flex flex-col gap-1 border border-gray-100">
                    <div class="flex justify-between items-center w-full">
                        <span class="text-xs font-bold text-gray-500">ผู้ใช้งาน</span>
                        <span id="display-user-desktop" class="text-xs font-black text-blue-600 uppercase">---</span>
                    </div>
                    <div class="flex justify-between items-center w-full mt-1 border-t border-gray-200 pt-1">
                        <span class="text-[10px] font-bold text-gray-400">สถานะเซิร์ฟเวอร์</span>
                        <div id="auth-status-desktop" class="text-[9px] bg-gray-200 text-gray-600 px-2 py-0.5 rounded-lg font-bold">กำลังเชื่อมต่อ</div>
                    </div>
                </div>
                <button onclick="handleLogout()" class="w-full py-2.5 bg-red-50 text-red-600 hover:bg-red-100 rounded-xl text-xs font-bold transition-colors flex items-center justify-center border border-red-100">
                    <i class="fa-solid fa-right-from-bracket mr-2"></i> ออกจากระบบ
                </button>
            </div>
        </aside>

        <!-- 2. MAIN CONTENT AREA -->
        <div class="flex-1 flex flex-col h-screen overflow-hidden relative">
            
            <!-- Mobile Top Header (Visible only on Mobile) -->
            <header class="md:hidden bg-blue-800 text-white p-4 shadow-md z-20 flex justify-between items-center shrink-0">
                <h1 class="text-xl font-bold flex items-center">
                    <img src="https://lh3.googleusercontent.com/d/1s93jOMu2iYhmBbcNAiMc0cNYDzsQ2izQ" alt="PK Tank" class="h-8 w-auto mr-2 object-contain">
                    PK Tank
                </h1>
                <div class="flex items-center gap-3">
                    <div class="flex flex-col items-end">
                        <span id="display-user-mobile" class="text-[10px] font-black text-blue-200 uppercase tracking-wider">---</span>
                        <div id="auth-status-mobile" class="text-[9px] bg-blue-700 px-1.5 py-0.5 rounded text-white font-bold">กำลังเชื่อมต่อ</div>
                    </div>
                    <button onclick="handleLogout()" class="text-blue-200 hover:text-white transition-colors bg-blue-900 w-8 h-8 rounded-full flex items-center justify-center">
                        <i class="fa-solid fa-right-from-bracket"></i>
                    </button>
                </div>
            </header>

            <!-- Scrollable Content View (แก้ไขเพิ่มระยะเว้นล่าง pb-24 เป็น pb-40) -->
            <main class="flex-1 overflow-y-auto p-4 md:p-8 pb-40 md:pb-8 w-full">
                <div class="max-w-5xl mx-auto">
                    
                    <!-- DASHBOARD VIEW -->
                    <div id="view-dashboard" class="tab-content active">
                        <div class="flex items-center justify-between mb-6">
                            <h2 class="text-2xl font-black text-gray-800 tracking-tight">แดชบอร์ดสรุปสถานะ</h2>
                        </div>
                        <div id="dashboard-container" class="space-y-4">
                            <div class="text-center py-12 text-gray-400"><i class="fa-solid fa-spinner fa-spin text-3xl"></i><br><span class="text-sm mt-2 block">กำลังโหลดข้อมูล...</span></div>
                        </div>
                    </div>

                    <!-- STOCK VIEW (สต็อกถัง) -->
                    <div id="view-stock" class="tab-content">
                        <div class="max-w-5xl mx-auto">
                            <h2 class="text-xl font-black text-gray-800 mb-6">รายการสต็อกถังทั้งหมด</h2>
                            
                            <!-- Filter & Search Controls -->
                            <div class="bg-white p-4 md:p-5 rounded-2xl shadow-sm border border-gray-100 mb-6 flex flex-col md:flex-row gap-3 md:gap-4">
                                <div class="flex-1 flex border border-gray-200 focus-within:ring-2 focus-within:ring-blue-500 rounded-xl overflow-hidden bg-gray-50">
                                    <span class="pl-4 py-3 text-gray-400"><i class="fa-solid fa-search"></i></span>
                                    <input type="text" id="search-stock-input" oninput="renderStockTable()" placeholder="ค้นหารหัสถัง..." class="w-full px-3 py-3 outline-none uppercase text-sm font-bold text-gray-700 bg-transparent">
                                </div>
                                <div class="w-full md:w-64 shrink-0 relative">
                                    <select id="filter-stock-status" onchange="renderStockTable()" class="w-full px-4 py-3 border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500 bg-blue-50 text-blue-800 text-sm font-bold appearance-none cursor-pointer">
                                        <option value="all">ทั้งหมด (All)</option>
                                        <option value="ready">ถังเปล่าพร้อมใช้</option>
                                        <option value="stock">บรรจุแล้วรอขาย</option>
                                        <option value="customer">ขายแล้วรอกลับ</option>
                                        <option value="inactive">ถังไม่พร้อมใช้งาน</option>
                                        <option value="loss">คาดการณ์สูญหาย</option>
                                    </select>
                                    <i class="fa-solid fa-chevron-down absolute right-4 top-1/2 transform -translate-y-1/2 text-blue-800 pointer-events-none text-xs"></i>
                                </div>
                            </div>

                            <!-- Data Table -->
                            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 overflow-hidden">
                                <div class="overflow-x-auto">
                                    <table class="w-full text-left border-collapse min-w-[600px]">
                                        <thead>
                                            <tr class="bg-gray-50 border-b border-gray-200 text-xs text-gray-500 uppercase tracking-wider">
                                                <th class="p-4 font-bold w-1/4">รหัสถัง</th>
                                                <th class="p-4 font-bold w-1/4">สถานะปัจจุบัน</th>
                                                <th class="p-4 font-bold w-1/4">อัปเดตล่าสุด</th>
                                                <th class="p-4 font-bold w-1/4 text-center">จำนวนวันคงค้าง</th>
                                            </tr>
                                        </thead>
                                        <tbody id="stock-table-body" class="divide-y divide-gray-100">
                                            <!-- Rows will be injected here by JS -->
                                        </tbody>
                                    </table>
                                </div>
                                <div id="stock-empty-state" class="text-center py-16 hidden">
                                    <i class="fa-solid fa-box-open text-gray-200 text-4xl mb-3"></i>
                                    <p class="text-gray-400 text-sm font-bold" id="stock-empty-text">ไม่พบข้อมูล</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- SCANNER VIEW -->
                    <div id="view-scan" class="tab-content">
                        <div class="max-w-xl mx-auto">
                            <h2 class="text-xl font-black text-gray-800 mb-6 text-center">สแกน QR Code / บันทึกข้อมูล</h2>
                            
                            <div class="bg-white p-5 md:p-8 rounded-2xl shadow-sm border border-gray-100">
                                <label class="block text-sm font-bold text-gray-700 mb-4 text-center uppercase tracking-wide">ประเภทการบันทึก</label>
                                
                                <!-- Dynamic Grid Layout -->
                                <div id="scan-action-container" class="grid grid-cols-3 gap-2 md:gap-4 mb-8">
                                    <button id="btn-action-receive" onclick="setScanAction('receive')" class="action-btn bg-blue-100 text-blue-800 border-2 border-blue-500 py-3 rounded-xl font-bold text-xs md:text-sm transition-all shadow-sm">
                                        <i class="fa-solid fa-download block text-xl md:text-2xl mb-1"></i> 1. รับเข้า
                                    </button>
                                    <button id="btn-action-pack" onclick="setScanAction('pack')" class="action-btn bg-gray-50 text-gray-500 border-2 border-transparent py-3 rounded-xl font-bold text-xs md:text-sm transition-all hover:bg-gray-100">
                                        <i class="fa-solid fa-box-open block text-xl md:text-2xl mb-1"></i> 2. บรรจุ
                                    </button>
                                    <button id="btn-action-dispatch" onclick="setScanAction('dispatch')" class="action-btn bg-gray-50 text-gray-500 border-2 border-transparent py-3 rounded-xl font-bold text-xs md:text-sm transition-all hover:bg-gray-100">
                                        <i class="fa-solid fa-truck block text-xl md:text-2xl mb-1"></i> 3. จ่ายออก
                                    </button>
                                </div>
                                <input type="hidden" id="current-action" value="receive">
                                
                                <!-- Camera UI -->
                                <div class="relative rounded-2xl overflow-hidden shadow-inner bg-black mb-6 min-h-[250px] md:min-h-[300px] border-[6px] border-gray-50">
                                    <div id="reader"></div>
                                </div>
                                
                                <!-- Fallback Actions -->
                                <div class="flex flex-col gap-3">
                                    <p class="text-[10px] text-red-500 text-center font-bold hidden bg-red-50 py-2 rounded-lg" id="camera-error-text">
                                        <i class="fa-solid fa-triangle-exclamation"></i> ไม่สามารถเปิดกล้องสดได้ กรุณาใช้ปุ่มเลือกรูปภาพด้านล่าง
                                    </p>
                                    
                                    <label for="qr-input-file" class="bg-gray-800 text-white px-4 py-4 rounded-xl text-sm cursor-pointer hover:bg-gray-700 transition-colors flex items-center justify-center font-bold shadow-md">
                                        <i class="fa-solid fa-image mr-2 text-lg"></i> สแกนจากรูปภาพ / คลังภาพ
                                    </label>
                                    <input type="file" id="qr-input-file" accept="image/*" class="hidden" onchange="handleFileUpload(event)">
                                </div>

                                <div class="flex items-center my-8">
                                    <div class="flex-grow border-t border-gray-200"></div>
                                    <span class="px-4 text-gray-400 text-xs font-bold uppercase tracking-wider">หรือกรอกรหัสถังเอง</span>
                                    <div class="flex-grow border-t border-gray-200"></div>
                                </div>

                                <div class="flex gap-2">
                                    <input type="text" id="manual-tank-id" placeholder="รหัสถัง (เช่น JSP PK001)" class="flex-1 px-4 py-3 border border-gray-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500 uppercase text-sm shadow-inner bg-gray-50">
                                    <button onclick="handleManualSubmit()" class="bg-blue-600 text-white px-6 py-3 rounded-xl font-bold text-sm shadow-md hover:bg-blue-700 transition-colors">ยืนยัน</button>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- MANAGE VIEW (จัดการถัง) -->
                    <div id="view-manage" class="tab-content">
                        <div class="max-w-5xl mx-auto">
                            <div class="flex justify-between items-center mb-6">
                                <h2 class="text-xl font-black text-gray-800">จัดการข้อมูลถัง</h2>
                                <button onclick="openSettingsModal()" class="bg-white text-gray-700 px-3 py-2 rounded-xl text-xs font-bold hover:bg-gray-50 transition-colors shadow-sm border border-gray-200">
                                    <i class="fa-solid fa-gear mr-1"></i> ตั้งค่าสูญหาย
                                </button>
                            </div>
                            
                            <!-- Filter & Search Controls -->
                            <div class="bg-white p-4 md:p-5 rounded-2xl shadow-sm border border-gray-100 mb-6 flex flex-col md:flex-row gap-3 md:gap-4">
                                <div class="flex-1 flex border border-gray-200 focus-within:ring-2 focus-within:ring-blue-500 rounded-xl overflow-hidden bg-gray-50">
                                    <span class="pl-4 py-3 text-gray-400"><i class="fa-solid fa-search"></i></span>
                                    <input type="text" id="search-manage-input" oninput="renderManageTable()" placeholder="ค้นหารหัสถัง..." class="w-full px-3 py-3 outline-none uppercase text-sm font-bold text-gray-700 bg-transparent">
                                </div>
                                <div class="w-full md:w-64 shrink-0 relative">
                                    <select id="filter-manage-status" onchange="renderManageTable()" class="w-full px-4 py-3 border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500 bg-blue-50 text-blue-800 text-sm font-bold appearance-none cursor-pointer">
                                        <option value="all">ทั้งหมด (All)</option>
                                        <option value="ready">ถังเปล่าพร้อมใช้</option>
                                        <option value="stock">บรรจุแล้วรอขาย</option>
                                        <option value="customer">ขายแล้วรอกลับ</option>
                                        <option value="inactive">ถังไม่พร้อมใช้งาน</option>
                                        <option value="loss">คาดการณ์สูญหาย</option>
                                    </select>
                                    <i class="fa-solid fa-chevron-down absolute right-4 top-1/2 transform -translate-y-1/2 text-blue-800 pointer-events-none text-xs"></i>
                                </div>
                            </div>

                            <!-- Data Table -->
                            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 overflow-hidden">
                                <div class="overflow-x-auto">
                                    <table class="w-full text-left border-collapse min-w-[600px]">
                                        <thead>
                                            <tr class="bg-gray-50 border-b border-gray-200 text-xs text-gray-500 uppercase tracking-wider">
                                                <th class="p-4 font-bold w-1/4">รหัสถัง</th>
                                                <th class="p-4 font-bold w-1/4">สถานะปัจจุบัน</th>
                                                <th class="p-4 font-bold w-1/4">อัปเดตล่าสุด</th>
                                                <th class="p-4 font-bold w-1/4 text-center">จัดการ</th>
                                            </tr>
                                        </thead>
                                        <tbody id="manage-table-body" class="divide-y divide-gray-100">
                                            <!-- Rows will be injected here by JS -->
                                        </tbody>
                                    </table>
                                </div>
                                <div id="manage-empty-state" class="text-center py-16 hidden">
                                    <i class="fa-solid fa-box-open text-gray-200 text-4xl mb-3"></i>
                                    <p class="text-gray-400 text-sm font-bold" id="manage-empty-text">ไม่พบข้อมูล</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- LABEL MAKER VIEW (สร้างเลเบลถัง) -->
                    <div id="view-label" class="tab-content">
                        <div class="max-w-6xl mx-auto">
                            <h2 class="text-xl font-black text-gray-800 mb-6">สร้างเอกสารป้ายเลเบลถัง (PDF ขนาด A5)</h2>
                            
                            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                                <!-- ฟอร์มกรอกข้อมูล (ฝั่งซ้าย) -->
                                <div class="lg:col-span-4 space-y-4">
                                    <div class="bg-white p-5 md:p-6 rounded-2xl shadow-sm border border-gray-100">
                                        <h3 class="text-sm font-bold text-gray-600 mb-4 border-b pb-2 uppercase tracking-wide"><i class="fa-solid fa-pen-to-square mr-2"></i>รายละเอียดเลเบล</h3>
                                        
                                        <div class="space-y-4">
                                            <div>
                                                <label class="block text-xs font-bold text-gray-500 mb-1">ชื่อผลิตภัณฑ์ / แบรนด์ (บน)</label>
                                                <input type="text" id="label-input-product" value="JSP" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 bg-gray-50 text-sm font-bold uppercase transition-colors" oninput="renderLabelPreview()" placeholder="เช่น JSP, ALC FOAM">
                                            </div>
                                            <div>
                                                <label class="block text-xs font-bold text-gray-500 mb-1">รหัสถัง (ล่าง)</label>
                                                <input type="text" id="label-input-tank" value="PK 001" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 bg-gray-50 text-sm font-bold uppercase transition-colors" oninput="renderLabelPreview()" placeholder="เช่น PK 001, PK 088">
                                            </div>
                                            <div>
                                                <label class="block text-xs font-bold text-gray-500 mb-1">ข้อความใน QR Code</label>
                                                <input type="text" id="label-input-qrtext" class="w-full px-4 py-3 border border-gray-200 rounded-xl bg-gray-100 text-sm font-bold text-gray-500 cursor-not-allowed" disabled>
                                            </div>
                                            <div>
                                                <label class="block text-xs font-bold text-gray-500 mb-1">วันที่แสดงบนเลเบล</label>
                                                <input type="date" id="label-input-date" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 bg-gray-50 text-sm font-bold transition-colors" onchange="renderLabelPreview()">
                                            </div>
                                            <div>
                                                <label class="block text-xs font-bold text-gray-500 mb-2">สีพื้นหลังด้านบน</label>
                                                <div class="flex items-center gap-3">
                                                    <input type="color" id="label-input-color" value="#ff0000" class="w-12 h-12 rounded cursor-pointer border-0 p-0 shrink-0" onchange="renderLabelPreview()">
                                                    <div class="flex flex-wrap gap-2">
                                                        <button type="button" title="แดง" onclick="document.getElementById('label-input-color').value='#ff0000'; renderLabelPreview();" class="w-8 h-8 bg-[#ff0000] rounded-full border border-gray-300 shadow-sm hover:scale-110 transition-transform"></button>
                                                        <button type="button" title="น้ำเงิน" onclick="document.getElementById('label-input-color').value='#0000ff'; renderLabelPreview();" class="w-8 h-8 bg-[#0000ff] rounded-full border border-gray-300 shadow-sm hover:scale-110 transition-transform"></button>
                                                        <button type="button" title="เหลือง" onclick="document.getElementById('label-input-color').value='#ffcc00'; renderLabelPreview();" class="w-8 h-8 bg-[#ffcc00] rounded-full border border-gray-300 shadow-sm hover:scale-110 transition-transform"></button>
                                                        <button type="button" title="เขียว" onclick="document.getElementById('label-input-color').value='#008000'; renderLabelPreview();" class="w-8 h-8 bg-[#008000] rounded-full border border-gray-300 shadow-sm hover:scale-110 transition-transform"></button>
                                                        <button type="button" title="ฟ้า" onclick="document.getElementById('label-input-color').value='#00bfff'; renderLabelPreview();" class="w-8 h-8 bg-[#00bfff] rounded-full border border-gray-300 shadow-sm hover:scale-110 transition-transform"></button>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>

                                        <button onclick="downloadLabelPDF()" class="w-full mt-6 bg-blue-600 text-white font-bold py-4 rounded-xl shadow-lg hover:bg-blue-700 transition-transform active:scale-95 text-sm flex justify-center items-center">
                                            <i class="fa-solid fa-file-pdf mr-2 text-lg"></i> ดาวน์โหลดเป็น PDF (A5)
                                        </button>
                                    </div>
                                </div>

                                <!-- พรีวิวตัวอย่าง (ฝั่งขวา) - แก้ไขให้ย่อตามขนาดหน้าจอ (Responsive Scale) -->
                                <div class="lg:col-span-8 bg-gray-200 p-4 md:p-8 rounded-2xl flex items-center justify-center border border-gray-300 shadow-inner overflow-hidden">
                                    
                                    <!-- ตัวคลุมสำหรับจัดการสเกลภาพให้พอดีหน้าจอ -->
                                    <div id="scale-wrapper" class="relative w-full max-w-[794px]" style="aspect-ratio: 794/559;">
                                        <div id="preview-scaler" class="absolute top-0 left-0" style="transform-origin: top left; transition: transform 0.2s ease-out;">
                                            <!-- Container หลักที่ขนาดเป๊ะกับ A5 (96dpi) เพื่อให้ Render PDF ออกมาคมกริบและไม่คลาดเคลื่อน -->
                                            <div id="label-preview-container" class="bg-white flex flex-col relative shrink-0" style="width: 794px; height: 559px; border: 12px solid black; font-family: Arial, Helvetica, sans-serif; box-sizing: border-box;">
                                                
                                                <!-- แถบด้านบน (สีและชื่อแบรนด์) -->
                                                <div id="label-top-bg" class="flex items-center justify-center bg-[#ff0000]" style="height: 50%; border-bottom: 12px solid black; box-sizing: border-box; overflow: hidden; padding: 0 30px;">
                                                    <div id="label-product-name" style="font-size: 150px; font-weight: 900; color: white; letter-spacing: 2px; text-transform: uppercase; white-space: nowrap;">JSP</div>
                                                </div>

                                                <!-- แถบด้านล่าง (รหัสถัง, QR Code, วันที่) -->
                                                <div class="flex relative" style="height: 50%; box-sizing: border-box;">
                                                    <div class="flex items-center justify-center" style="width: 70%; border-right: 12px solid black; box-sizing: border-box; overflow: hidden; padding: 0 30px;">
                                                        <div id="label-tank-id" style="font-size: 160px; font-weight: 900; color: black; letter-spacing: -4px; text-transform: uppercase; white-space: nowrap;">PK 001</div>
                                                    </div>
                                                    <div class="flex items-center justify-center relative" style="width: 30%; box-sizing: border-box;">
                                                        <div id="label-qrcode" style="padding: 10px;"></div>
                                                    </div>
                                                    <div id="label-date" style="position: absolute; bottom: 8px; right: 12px; font-size: 20px; font-weight: 900; color: black;">Date: 04/03/2026</div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>

                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- SEARCH VIEW -->
                    <div id="view-search" class="tab-content">
                        <div class="max-w-5xl mx-auto">
                            <h2 class="text-xl font-black text-gray-800 mb-6">ค้นหาและประวัติ</h2>
                            
                            <!-- Filter & Search Controls -->
                            <div class="bg-white p-4 md:p-5 rounded-2xl shadow-sm border border-gray-100 mb-6 flex flex-col md:flex-row gap-3 md:gap-4">
                                <div class="flex-1 flex border border-gray-200 focus-within:ring-2 focus-within:ring-blue-500 rounded-xl overflow-hidden bg-gray-50">
                                    <span class="pl-4 py-3 text-gray-400"><i class="fa-solid fa-search"></i></span>
                                    <input type="text" id="search-history-input" oninput="renderSearchTable()" placeholder="ค้นหารหัสถังที่ต้องการประวัติ..." class="w-full px-3 py-3 outline-none uppercase text-sm font-bold text-gray-700 bg-transparent">
                                </div>
                                <div class="w-full md:w-64 shrink-0 relative">
                                    <select id="filter-history-status" onchange="renderSearchTable()" class="w-full px-4 py-3 border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500 bg-blue-50 text-blue-800 text-sm font-bold appearance-none cursor-pointer">
                                        <option value="all">ทั้งหมด (All)</option>
                                        <option value="ready">ถังเปล่าพร้อมใช้</option>
                                        <option value="stock">บรรจุแล้วรอขาย</option>
                                        <option value="customer">ขายแล้วรอกลับ</option>
                                        <option value="inactive">ถังไม่พร้อมใช้งาน</option>
                                        <option value="loss">คาดการณ์สูญหาย</option>
                                    </select>
                                    <i class="fa-solid fa-chevron-down absolute right-4 top-1/2 transform -translate-y-1/2 text-blue-800 pointer-events-none text-xs"></i>
                                </div>
                                <button onclick="exportToExcel()" class="w-full md:w-auto bg-green-600 text-white px-5 py-3 rounded-xl font-bold hover:bg-green-700 transition-colors shadow-sm flex items-center justify-center shrink-0">
                                    <i class="fa-solid fa-file-excel mr-2"></i> ส่งออก Excel
                                </button>
                            </div>

                            <!-- Data Table -->
                            <div class="bg-white rounded-2xl shadow-sm border border-gray-100 overflow-hidden">
                                <div class="overflow-x-auto">
                                    <table class="w-full text-left border-collapse min-w-[600px]">
                                        <thead>
                                            <tr class="bg-gray-50 border-b border-gray-200 text-xs text-gray-500 uppercase tracking-wider">
                                                <th class="p-4 font-bold w-1/4">รหัสถัง</th>
                                                <th class="p-4 font-bold w-1/4">สถานะปัจจุบัน</th>
                                                <th class="p-4 font-bold w-1/4">อัปเดตล่าสุด</th>
                                                <th class="p-4 font-bold w-1/4 text-center">ดูประวัติ</th>
                                            </tr>
                                        </thead>
                                        <tbody id="search-table-body" class="divide-y divide-gray-100">
                                            <!-- Rows will be injected here by JS -->
                                        </tbody>
                                    </table>
                                </div>
                                <div id="search-empty-state" class="text-center py-16 hidden">
                                    <i class="fa-solid fa-clock-rotate-left text-gray-200 text-4xl mb-3"></i>
                                    <p class="text-gray-400 text-sm font-bold" id="search-empty-text">ไม่พบข้อมูล</p>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </main>

            <!-- 3. BOTTOM NAV (MOBILE ONLY) -->
            <nav class="md:hidden fixed bottom-0 w-full bg-white border-t border-gray-200 pb-safe z-40 shadow-[0_-4px_6px_-1px_rgba(0,0,0,0.05)]">
                <div class="flex justify-between items-end max-w-lg mx-auto px-1">
                    <button onclick="switchTab('dashboard')" id="nav-mobile-dashboard" class="nav-btn-mobile flex-1 py-3 text-center text-blue-600 font-bold flex flex-col items-center transition-colors">
                        <i class="fa-solid fa-chart-pie text-xl mb-1"></i>
                        <span class="text-[9px]">Dashboard</span>
                    </button>
                    <button onclick="switchTab('stock')" id="nav-mobile-stock" class="nav-btn-mobile flex-1 py-3 text-center text-gray-400 font-bold flex flex-col items-center transition-colors">
                        <i class="fa-solid fa-layer-group text-xl mb-1"></i>
                        <span class="text-[9px]">สต็อกถัง</span>
                    </button>
                    <button onclick="switchTab('scan')" id="nav-mobile-scan" class="nav-btn-mobile flex-1 py-3 text-center text-gray-400 font-bold flex flex-col items-center transition-colors relative">
                        <div class="bg-blue-600 text-white w-12 h-12 rounded-full flex items-center justify-center absolute -top-5 shadow-lg border-4 border-[#f9fafb] transform transition-transform active:scale-95">
                            <i class="fa-solid fa-qrcode text-xl"></i>
                        </div>
                        <span class="text-[9px] mt-7 text-gray-600">Scan</span>
                    </button>
                    <button onclick="switchTab('manage')" id="nav-mobile-manage" class="nav-btn-mobile flex-1 py-3 text-center text-gray-400 font-bold flex flex-col items-center transition-colors">
                        <i class="fa-solid fa-gear text-xl mb-1"></i>
                        <span class="text-[9px]">จัดการ</span>
                    </button>
                    <!-- ป้าย Label มือถือ (Admin Only) -->
                    <button onclick="switchTab('label')" id="nav-mobile-label" class="nav-btn-mobile flex-1 py-3 text-center text-gray-400 font-bold flex flex-col items-center transition-colors">
                        <i class="fa-solid fa-tags text-xl mb-1"></i>
                        <span class="text-[9px]">สร้างเลเบล</span>
                    </button>
                    <button onclick="switchTab('search')" id="nav-mobile-search" class="nav-btn-mobile flex-1 py-3 text-center text-gray-400 font-bold flex flex-col items-center transition-colors">
                        <i class="fa-solid fa-magnifying-glass text-xl mb-1"></i>
                        <span class="text-[9px]">Search</span>
                    </button>
                </div>
            </nav>

        </div>
    </div>

    <!-- Condition Modal -->
    <div id="condition-modal" class="fixed inset-0 bg-black bg-opacity-60 backdrop-blur-sm flex items-center justify-center z-50 hidden px-4 py-4">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md p-6 md:p-8 transform transition-all max-h-[95vh] overflow-y-auto">
            <div class="flex items-center justify-between border-b border-gray-100 pb-4 mb-6">
                <h3 class="text-xl font-black text-gray-800">ประเมินสภาพถัง</h3>
                <span class="bg-blue-100 text-blue-800 text-xs font-bold px-3 py-1 rounded-lg">รับเข้า</span>
            </div>
            
            <p class="text-sm text-gray-500 font-bold mb-6 flex justify-between bg-gray-50 p-3 rounded-xl border border-gray-100">
                <span>รหัสถัง:</span>
                <span id="modal-tank-id" class="text-blue-600 font-black text-base">---</span>
            </p>
            
            <div class="space-y-5 mb-8">
                <div>
                    <p class="text-xs font-bold text-gray-400 mb-2 uppercase tracking-wider">1. สภาพวาล์ว</p>
                    <div class="flex gap-3">
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-blue-50 has-[:checked]:bg-blue-50 has-[:checked]:border-blue-500 has-[:checked]:text-blue-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-valve" value="ดี" class="hidden" checked> ดี
                        </label>
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-red-50 has-[:checked]:bg-red-50 has-[:checked]:border-red-500 has-[:checked]:text-red-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-valve" value="รั่วซึม" class="hidden"> รั่วซึม
                        </label>
                    </div>
                </div>
                <div>
                    <p class="text-xs font-bold text-gray-400 mb-2 uppercase tracking-wider">2. โครงสร้าง</p>
                    <div class="flex gap-3">
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-blue-50 has-[:checked]:bg-blue-50 has-[:checked]:border-blue-500 has-[:checked]:text-blue-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-struct" value="ดี" class="hidden" checked> ดี
                        </label>
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-red-50 has-[:checked]:bg-red-50 has-[:checked]:border-red-500 has-[:checked]:text-red-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-struct" value="เป็นสนิม" class="hidden"> สนิม
                        </label>
                    </div>
                </div>
                <div>
                    <p class="text-xs font-bold text-gray-400 mb-2 uppercase tracking-wider">3. ฐาน</p>
                    <div class="flex gap-3">
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-blue-50 has-[:checked]:bg-blue-50 has-[:checked]:border-blue-500 has-[:checked]:text-blue-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-base" value="ดี" class="hidden" checked> ดี
                        </label>
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-red-50 has-[:checked]:bg-red-50 has-[:checked]:border-red-500 has-[:checked]:text-red-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-base" value="ชำรุด" class="hidden"> ชำรุด
                        </label>
                    </div>
                </div>
                <div>
                    <p class="text-xs font-bold text-gray-400 mb-2 uppercase tracking-wider">4. ความพร้อมการใช้งาน</p>
                    <div class="flex gap-3 flex-col sm:flex-row">
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-blue-50 has-[:checked]:bg-blue-50 has-[:checked]:border-blue-500 has-[:checked]:text-blue-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-ready" value="พร้อมนำไปบรรจุ" class="hidden" checked> พร้อม
                        </label>
                        <label class="flex-1 border-2 border-gray-200 rounded-xl p-3 text-center cursor-pointer hover:bg-red-50 has-[:checked]:bg-red-50 has-[:checked]:border-red-500 has-[:checked]:text-red-700 transition-all font-bold text-gray-600">
                            <input type="radio" name="cond-ready" value="ไม่พร้อมนำไปบรรจุ" class="hidden"> ไม่พร้อม
                        </label>
                    </div>
                </div>
                <input type="text" id="cond-note" placeholder="หมายเหตุเพิ่มเติม (ถ้ามี)..." class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-white bg-gray-50 text-sm transition-colors">
            </div>

            <div class="flex gap-3">
                <button onclick="closeConditionModal()" class="flex-1 px-4 py-4 bg-gray-100 text-gray-700 rounded-xl font-bold hover:bg-gray-200 transition-colors">ยกเลิก</button>
                <button onclick="submitTankCondition()" class="flex-1 px-4 py-4 bg-blue-600 text-white rounded-xl font-bold shadow-md hover:bg-blue-700 transition-colors">บันทึกข้อมูล</button>
            </div>
        </div>
    </div>

    <!-- Edit Tank Modal -->
    <div id="edit-tank-modal" class="fixed inset-0 bg-black bg-opacity-60 backdrop-blur-sm flex items-center justify-center z-50 hidden px-4 py-4">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md p-6 md:p-8 transform transition-all max-h-[95vh] overflow-y-auto">
            <div class="flex items-center justify-between border-b border-gray-100 pb-4 mb-6">
                <h3 class="text-xl font-black text-gray-800">แก้ไขข้อมูลถัง</h3>
            </div>
            
            <p class="text-sm text-gray-500 font-bold mb-6 flex justify-between bg-gray-50 p-3 rounded-xl border border-gray-100">
                <span>รหัสถัง:</span>
                <span id="edit-modal-tank-id" class="text-blue-600 font-black text-base">---</span>
            </p>
            
            <div class="mb-6">
                <label class="block text-xs font-bold text-gray-400 mb-2 uppercase tracking-wider">ปรับสถานะปัจจุบัน</label>
                <select id="edit-tank-status" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-white bg-gray-50 text-sm font-bold text-gray-700 transition-colors cursor-pointer">
                    <option value="Ready to Use">ถังเปล่าพร้อมใช้</option>
                    <option value="Stock">บรรจุแล้วรอขาย</option>
                    <option value="Customer">ขายแล้วรอกลับ</option>
                    <option value="Inactive">ถังไม่พร้อมใช้งาน</option>
                    <option value="Loss">คาดการณ์สูญหาย</option>
                </select>
            </div>

            <!-- New: Custom Thresholds per Tank -->
            <div class="mb-6 border-t border-gray-100 pt-4">
                <label class="flex items-center gap-2 cursor-pointer mb-3">
                    <input type="checkbox" id="edit-use-custom-thresholds" class="w-4 h-4 text-blue-600 rounded focus:ring-blue-500 cursor-pointer" onchange="toggleCustomThresholdInputs()">
                    <span class="text-sm font-bold text-gray-700">กำหนดวันสูญหายเฉพาะถังใบนี้</span>
                </label>
                
                <div id="custom-threshold-inputs" class="hidden space-y-3 p-4 bg-blue-50 border border-blue-100 rounded-xl">
                    <div class="flex items-center justify-between">
                        <span class="text-xs font-bold text-gray-600">ถังเปล่าพร้อมใช้:</span>
                        <div class="flex items-center"><input type="number" id="edit-custom-ready" class="w-16 px-2 py-1 text-center border border-gray-300 rounded focus:outline-none focus:border-blue-500 text-xs font-bold mr-1" min="1"> <span class="text-xs text-gray-500">วัน</span></div>
                    </div>
                    <div class="flex items-center justify-between">
                        <span class="text-xs font-bold text-gray-600">บรรจุแล้วรอขาย:</span>
                        <div class="flex items-center"><input type="number" id="edit-custom-stock" class="w-16 px-2 py-1 text-center border border-gray-300 rounded focus:outline-none focus:border-blue-500 text-xs font-bold mr-1" min="1"> <span class="text-xs text-gray-500">วัน</span></div>
                    </div>
                    <div class="flex items-center justify-between">
                        <span class="text-xs font-bold text-gray-600">ขายแล้วรอกลับ:</span>
                        <div class="flex items-center"><input type="number" id="edit-custom-customer" class="w-16 px-2 py-1 text-center border border-gray-300 rounded focus:outline-none focus:border-blue-500 text-xs font-bold mr-1" min="1"> <span class="text-xs text-gray-500">วัน</span></div>
                    </div>
                </div>
            </div>

            <div class="flex flex-col gap-3">
                <div class="flex gap-3">
                    <button onclick="closeEditTankModal()" class="flex-1 px-4 py-4 bg-gray-100 text-gray-700 rounded-xl font-bold hover:bg-gray-200 transition-colors">ยกเลิก</button>
                    <button onclick="submitEditTank()" class="flex-1 px-4 py-4 bg-blue-600 text-white rounded-xl font-bold shadow-md hover:bg-blue-700 transition-colors">บันทึกการแก้ไข</button>
                </div>
                <button onclick="confirmDeleteTank()" class="w-full px-4 py-3 bg-red-50 text-red-600 rounded-xl font-bold hover:bg-red-100 transition-colors border border-red-100 mt-2"><i class="fa-solid fa-trash-can mr-1"></i> ลบข้อมูลถังนี้ถาวร</button>
            </div>
        </div>
    </div>

    <!-- Settings Modal -->
    <div id="settings-modal" class="fixed inset-0 bg-black bg-opacity-60 backdrop-blur-sm flex items-center justify-center z-50 hidden px-4 py-4">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md p-6 md:p-8 transform transition-all">
            <h3 class="text-xl font-black text-gray-800 mb-6 border-b border-gray-100 pb-4"><i class="fa-solid fa-gear mr-2 text-blue-600"></i>ตั้งค่าวันคาดการณ์สูญหาย</h3>
            <div class="space-y-4 mb-6">
                <div>
                    <label class="block text-xs font-bold text-gray-500 mb-1">ระยะเวลาคงค้าง: ถังเปล่าพร้อมใช้ (วัน)</label>
                    <input type="number" id="setting-days-ready" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-white bg-gray-50 text-sm font-bold" min="1">
                </div>
                <div>
                    <label class="block text-xs font-bold text-gray-500 mb-1">ระยะเวลาคงค้าง: บรรจุแล้วรอขาย (วัน)</label>
                    <input type="number" id="setting-days-stock" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-white bg-gray-50 text-sm font-bold" min="1">
                </div>
                <div>
                    <label class="block text-xs font-bold text-gray-500 mb-1">ระยะเวลาคงค้าง: ขายแล้วรอกลับ (วัน)</label>
                    <input type="number" id="setting-days-customer" class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:outline-none focus:border-blue-500 focus:bg-white bg-gray-50 text-sm font-bold" min="1">
                </div>
            </div>
            <div class="flex gap-3">
                <button onclick="closeSettingsModal()" class="flex-1 px-4 py-4 bg-gray-100 text-gray-700 rounded-xl font-bold hover:bg-gray-200 transition-colors">ยกเลิก</button>
                <button onclick="submitSettings()" class="flex-1 px-4 py-4 bg-blue-600 text-white rounded-xl font-bold shadow-md hover:bg-blue-700 transition-colors">บันทึกการตั้งค่า</button>
            </div>
        </div>
    </div>

    <!-- History Modal -->
    <div id="history-modal" class="fixed inset-0 bg-black bg-opacity-60 backdrop-blur-sm flex items-center justify-center z-50 hidden px-4 py-4">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md p-6 md:p-8 transform transition-all max-h-[95vh] flex flex-col">
            <div class="flex items-center justify-between border-b border-gray-100 pb-4 mb-4 shrink-0">
                <h3 class="text-xl font-black text-gray-800"><i class="fa-solid fa-clock-rotate-left text-blue-600 mr-2"></i>ประวัติการทำงาน</h3>
                <button onclick="closeHistoryModal()" class="text-gray-400 hover:text-gray-600 transition-colors">
                    <i class="fa-solid fa-xmark text-2xl"></i>
                </button>
            </div>
            
            <div class="overflow-y-auto flex-1 pr-2 custom-scrollbar" id="history-modal-content">
                <!-- History details injected here -->
            </div>

            <div class="mt-4 pt-4 border-t border-gray-100 shrink-0">
                <button onclick="closeHistoryModal()" class="w-full px-4 py-4 bg-gray-100 text-gray-700 rounded-xl font-bold hover:bg-gray-200 transition-colors">ปิดหน้าต่าง</button>
            </div>
        </div>
    </div>

    <!-- Firebase SDK Setup -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, doc, setDoc, getDoc, deleteDoc, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        const firebaseConfig = {
            apiKey: "AIzaSyBUSW7UlE_3tJQoRE6UM-IZRK51U7bUA78",
            authDomain: "pk-tank-393ee.firebaseapp.com",
            projectId: "pk-tank-393ee",
            storageBucket: "pk-tank-393ee.firebasestorage.app",
            messagingSenderId: "258998836085",
            appId: "1:258998836085:web:426de6575f10d74b01113c",
            measurementId: "G-3FV2TS5SSJ"
        };
        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);
        const db = getFirestore(app);
        const appId = 'pk-tank-393ee';

        // Global State
        window.globalTanks = [];
        window.currentUser = null; 
        
        // App State
        window.lossThresholds = { ready: 30, stock: 45, customer: 7 };
        window.editingTankId = null;
        let html5QrCode = null;
        let pendingTankId = null;
        let labelQrCodeObj = null; // ตัวแปรสำหรับ QR Code ในหน้าสร้าง Label
        
        // Custom Auth State
        window.appUser = null; 
        window.appRole = null; 

        // Database of Roles
        const SYSTEM_USERS = {
            'ADMIN': { pass: 'Admin', role: 'admin' },
            'RM': { pass: '123', role: 'rm' },
            'PACKING': { pass: '123', role: 'packing' },
            'WH': { pass: '123', role: 'wh' }
        };

        // Initialize Label Date to Today
        document.addEventListener('DOMContentLoaded', () => {
            const today = new Date();
            const yyyy = today.getFullYear();
            const mm = String(today.getMonth() + 1).padStart(2, '0');
            const dd = String(today.getDate()).padStart(2, '0');
            const dateInput = document.getElementById('label-input-date');
            if(dateInput) {
                dateInput.value = `${yyyy}-${mm}-${dd}`;
            }
        });

        // --- AUTHENTICATION LOGIC ---
        window.togglePasswordVisibility = () => {
            const passInput = document.getElementById('login-pass');
            const icon = document.getElementById('toggle-pass-icon');
            if (passInput.type === 'password') {
                passInput.type = 'text';
                icon.classList.replace('fa-eye', 'fa-eye-slash');
            } else {
                passInput.type = 'password';
                icon.classList.replace('fa-eye-slash', 'fa-eye');
            }
        };

        window.handleLogin = () => {
            const userInput = document.getElementById('login-user').value.trim().toUpperCase();
            const passInput = document.getElementById('login-pass').value;

            if (SYSTEM_USERS[userInput] && SYSTEM_USERS[userInput].pass === passInput) {
                window.appUser = userInput === 'ADMIN' ? 'Admin' : document.getElementById('login-user').value.trim();
                window.appRole = SYSTEM_USERS[userInput].role;
                
                document.getElementById('display-user-desktop').innerText = window.appUser;
                document.getElementById('display-user-mobile').innerText = window.appUser;

                document.getElementById('login-screen').style.display = 'none';
                document.getElementById('app-wrapper').style.display = 'flex';
                
                applyPermissions();
                
                renderDashboard();
                switchTab('dashboard');
                
                document.getElementById('login-user').value = '';
                document.getElementById('login-pass').value = '';
            } else {
                Swal.fire({ icon: 'error', title: 'เข้าสู่ระบบล้มเหลว', text: 'ชื่อผู้ใช้งานหรือรหัสผ่านไม่ถูกต้อง', confirmButtonColor: '#2563eb' });
            }
        };

        window.handleLogout = () => {
            Swal.fire({
                title: 'ออกจากระบบ?',
                icon: 'question',
                showCancelButton: true,
                confirmButtonColor: '#2563eb',
                cancelButtonColor: '#9ca3af',
                confirmButtonText: 'ออกจากระบบ',
                cancelButtonText: 'ยกเลิก'
            }).then((result) => {
                if (result.isConfirmed) {
                    window.appUser = null;
                    window.appRole = null;
                    stopScanner();
                    document.getElementById('app-wrapper').style.display = 'none';
                    document.getElementById('login-screen').style.display = 'flex';
                }
            });
        };

        function applyPermissions() {
            // Nav elements
            const manageNavDesktop = document.getElementById('nav-desktop-manage');
            const manageNavMobile = document.getElementById('nav-mobile-manage');
            const labelNavDesktop = document.getElementById('nav-desktop-label');
            const labelNavMobile = document.getElementById('nav-mobile-label');
            
            // Scan action buttons
            const scanContainer = document.getElementById('scan-action-container');
            const btnReceive = document.getElementById('btn-action-receive');
            const btnPack = document.getElementById('btn-action-pack');
            const btnDispatch = document.getElementById('btn-action-dispatch');

            if (window.appRole === 'admin') {
                if(manageNavDesktop) manageNavDesktop.style.display = 'flex';
                if(manageNavMobile) manageNavMobile.style.display = 'flex';
                if(labelNavDesktop) labelNavDesktop.style.display = 'flex';
                if(labelNavMobile) labelNavMobile.style.display = 'flex';
                
                scanContainer.className = 'grid grid-cols-3 gap-2 md:gap-4 mb-8';
                btnReceive.style.display = 'block';
                btnPack.style.display = 'block';
                btnDispatch.style.display = 'block';
                
                setScanAction('receive');
            } else {
                if(manageNavDesktop) manageNavDesktop.style.display = 'none';
                if(manageNavMobile) manageNavMobile.style.display = 'none';
                if(labelNavDesktop) labelNavDesktop.style.display = 'none';
                if(labelNavMobile) labelNavMobile.style.display = 'none';
                
                scanContainer.className = 'grid grid-cols-1 gap-2 md:gap-4 mb-8 max-w-xs mx-auto';
                btnReceive.style.display = 'none';
                btnPack.style.display = 'none';
                btnDispatch.style.display = 'none';

                if (window.appRole === 'rm') {
                    btnReceive.style.display = 'block';
                    setScanAction('receive');
                } else if (window.appRole === 'packing') {
                    btnPack.style.display = 'block';
                    setScanAction('pack');
                } else if (window.appRole === 'wh') {
                    btnDispatch.style.display = 'block';
                    setScanAction('dispatch');
                }
            }
        }

        // Update UI for Auth Status
        function updateAuthUI(status, isError = false) {
            const mob = document.getElementById('auth-status-mobile');
            const desk = document.getElementById('auth-status-desktop');
            
            if (mob) {
                mob.innerText = status;
                mob.className = `text-[9px] px-1.5 py-0.5 rounded text-white font-bold ${isError ? 'bg-red-600' : 'bg-green-500'}`;
            }
            if (desk) {
                desk.innerText = status;
                desk.className = `text-[9px] px-2 py-0.5 rounded-lg font-bold ${isError ? 'bg-red-100 text-red-700' : 'bg-green-100 text-green-700'}`;
            }
        }

        // 1. Firebase Auth Init
        onAuthStateChanged(auth, (user) => {
            if (user) {
                window.currentUser = user;
                updateAuthUI("ออนไลน์", false);
                
                const configRef = doc(db, 'artifacts', appId, 'public', 'data', 'settings', 'thresholds');
                onSnapshot(configRef, (docSnap) => {
                    if(docSnap.exists()) {
                        window.lossThresholds = { ...window.lossThresholds, ...docSnap.data() };
                        if(window.globalTanks.length > 0 && window.appUser) {
                            if(document.getElementById('view-dashboard').classList.contains('active')) renderDashboard();
                            if(document.getElementById('view-stock').classList.contains('active')) renderStockTable();
                            if(document.getElementById('view-manage').classList.contains('active')) renderManageTable();
                        }
                    }
                });

                const tanksRef = collection(db, 'artifacts', appId, 'public', 'data', 'tanks');
                onSnapshot(tanksRef, (snapshot) => {
                    window.globalTanks = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                    
                    if (window.appUser) {
                        if(document.getElementById('view-dashboard').classList.contains('active')) renderDashboard();
                        if(document.getElementById('view-stock').classList.contains('active')) renderStockTable();
                        if(document.getElementById('view-manage').classList.contains('active')) renderManageTable();
                        if(document.getElementById('view-search').classList.contains('active')) renderSearchTable();
                    }
                }, (error) => {
                    console.error("Firestore error:", error);
                    document.getElementById('dashboard-container').innerHTML = `<div class="p-4 bg-red-100 text-red-700 rounded-xl text-center text-xs">เกิดข้อผิดพลาดในการโหลดข้อมูล: ${error.code}</div>`;
                });
            }
        });
        
        signInAnonymously(auth).catch(err => {
            updateAuthUI("เชื่อมต่อล้มเหลว", true);
        });

        // --- LABEL GENERATOR LOGIC ---
        window.adjustLabelScale = () => {
            const scaleWrapper = document.getElementById('scale-wrapper');
            const scaler = document.getElementById('preview-scaler');
            if (scaleWrapper && scaler) {
                const currentWidth = scaleWrapper.clientWidth;
                // คำนวณสเกลเทียบกับความกว้างต้นฉบับ 794px
                const scale = currentWidth / 794;
                scaler.style.transform = `scale(${scale})`;
            }
        };

        // ตรวจจับการย่อขยายหน้าต่าง เพื่ออัปเดตสเกลพรีวิว
        window.addEventListener('resize', () => {
            if (document.getElementById('view-label').classList.contains('active')) {
                window.adjustLabelScale();
            }
        });

        window.renderLabelPreview = () => {
            const product = document.getElementById('label-input-product').value || 'JSP';
            const tank = document.getElementById('label-input-tank').value || 'PK 001';
            const color = document.getElementById('label-input-color').value || '#ff0000';
            
            const dateVal = document.getElementById('label-input-date').value;
            let dateStr = "";
            if(dateVal) {
                const parts = dateVal.split('-'); // YYYY-MM-DD
                dateStr = `${parts[2]}/${parts[1]}/${parts[0]}`;
            }

            // Update DOM Elements for Preview
            const productEl = document.getElementById('label-product-name');
            const tankEl = document.getElementById('label-tank-id');
            
            productEl.innerText = product;
            tankEl.innerText = tank;
            document.getElementById('label-top-bg').style.backgroundColor = color;
            document.getElementById('label-date').innerText = `Date: ${dateStr}`;

            // --- Auto-scale Font Size Logic ---
            // รีเซ็ตขนาดกลับไปเป็นขนาดสูงสุดก่อนเพื่อวัดความกว้างที่แท้จริง
            productEl.style.fontSize = '150px';
            tankEl.style.fontSize = '160px';

            // คำนวณปรับย่อขนาดตัวอักษรของ "ชื่อผลิตภัณฑ์" ไม่ให้ล้นกรอบ (ความกว้างสุด ~730px)
            const maxProductWidth = 794 - 60; 
            if (productEl.scrollWidth > maxProductWidth) {
                const newProductSize = Math.floor(150 * (maxProductWidth / productEl.scrollWidth));
                productEl.style.fontSize = `${newProductSize}px`;
            }

            // คำนวณปรับย่อขนาดตัวอักษรของ "รหัสถัง" ไม่ให้ล้นกรอบ (ความกว้างสุด ~500px)
            const maxTankWidth = (794 * 0.70) - 60; 
            if (tankEl.scrollWidth > maxTankWidth) {
                const newTankSize = Math.floor(160 * (maxTankWidth / tankEl.scrollWidth));
                tankEl.style.fontSize = `${newTankSize}px`;
            }

            // Create QR Text String (e.g. "JSP PK 001")
            const qrText = `${product} ${tank}`.replace(/\s+/g, ' ').trim();
            document.getElementById('label-input-qrtext').value = qrText;

            // Generate QR Code inside the preview container
            const qrContainer = document.getElementById('label-qrcode');
            qrContainer.innerHTML = ''; // Clear old QR code
            
            labelQrCodeObj = new QRCode(qrContainer, {
                text: qrText,
                width: 170,  // ขนาดพิกเซล QR Code แบบคมชัดสำหรับปรินท์
                height: 170,
                colorDark : "#000000",
                colorLight : "#ffffff",
                correctLevel : QRCode.CorrectLevel.H
            });

            // ปรับขนาดการแสดงผลให้พอดีหน้าจอ
            setTimeout(() => { window.adjustLabelScale(); }, 50);
        };

        window.downloadLabelPDF = async () => {
            Swal.fire({
                title: 'กำลังสร้าง PDF...',
                text: 'กรุณารอสักครู่',
                allowOutsideClick: false,
                didOpen: () => { Swal.showLoading(); }
            });

            try {
                // ปิด Scale ชั่วคราวเพื่อให้จับภาพได้ขนาดเต็ม 100%
                const scaler = document.getElementById('preview-scaler');
                const oldTransform = scaler.style.transform;
                scaler.style.transform = 'scale(1)';
                
                const element = document.getElementById('label-preview-container');
                // ใช้ html2canvas จับภาพ Container ของ Label (ปรับสเกลเพื่อความคมชัด)
                const canvas = await html2canvas(element, { scale: 3, useCORS: true });
                const imgData = canvas.toDataURL('image/png');
                
                // คืนค่า Scale กลับไป
                scaler.style.transform = oldTransform;
                
                // สร้างไฟล์ PDF ด้วย jsPDF (ขนาด A5 แนวนอน, หน่วยมิลลิเมตร)
                const { jsPDF } = window.jspdf;
                const pdf = new jsPDF('l', 'mm', 'a5'); 
                
                // นำภาพที่วาดไปแปะลงหน้า PDF ขนาด 210 x 148 mm
                pdf.addImage(imgData, 'PNG', 0, 0, 210, 148);
                
                const product = document.getElementById('label-input-product').value || 'Tank';
                const tank = document.getElementById('label-input-tank').value || '001';
                pdf.save(`Label_${product}_${tank}.pdf`);
                
                Swal.close();
                Swal.fire({ icon: 'success', title: 'ดาวน์โหลดสำเร็จ!', timer: 1500, showConfirmButton: false });
            } catch (error) {
                console.error("PDF Error:", error);
                Swal.fire('ข้อผิดพลาด', 'ไม่สามารถสร้างไฟล์ PDF ได้', 'error');
            }
        };

        // --- Core Functions ---
        function calculateDays(timestampMs) {
            if (!timestampMs) return 0;
            return Math.floor(Math.abs(Date.now() - timestampMs) / (1000 * 60 * 60 * 24));
        }

        function getExpectedLossInfo(status, days, customThresholds = null) {
            const thresholds = customThresholds || window.lossThresholds;
            if (status === 'Ready to Use' && days > thresholds.ready) return 'คาดการณ์หายในโรงงาน';
            if (status === 'Stock' && days > thresholds.stock) return 'คาดการณ์หายในคลังสินค้า';
            if (status === 'Customer' && days > thresholds.customer) return 'คาดการณ์หายระหว่างขนส่ง';
            return null;
        }

        function renderDashboard() {
            const container = document.getElementById('dashboard-container');
            if (window.globalTanks.length === 0) {
                container.innerHTML = `<div class="text-center py-16 bg-white rounded-2xl border border-gray-100 shadow-sm"><i class="fa-solid fa-folder-open text-gray-200 text-4xl mb-3"></i><p class="text-gray-400 text-sm font-bold">ยังไม่มีข้อมูลถังในระบบ</p></div>`;
                return;
            }

            let counts = { ready: 0, stock: 0, customer: 0, inactive: 0, loss: 0 };
            const totalTanks = window.globalTanks.length;

            window.globalTanks.forEach(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);

                if (lossReason || tank.status === 'Loss') {
                    counts.loss++;
                } else if (tank.status === 'Inactive') {
                    counts.inactive++;
                } else if (tank.status === 'Ready to Use') {
                    counts.ready++;
                } else if (tank.status === 'Stock') {
                    counts.stock++;
                } else if (tank.status === 'Customer') {
                    counts.customer++;
                }
            });

            container.innerHTML = `
                <div class="mb-4 bg-gradient-to-r from-blue-700 to-blue-900 rounded-2xl p-5 md:p-6 text-white shadow-md flex items-center justify-between transition-transform hover:scale-[1.01]">
                    <div class="flex items-center gap-4 md:gap-6">
                        <div class="bg-white/20 w-14 h-14 md:w-16 md:h-16 flex items-center justify-center rounded-full shrink-0">
                            <i class="fa-solid fa-boxes-stacked text-white text-2xl md:text-3xl"></i>
                        </div>
                        <div>
                            <div class="text-base md:text-lg text-blue-50 font-bold">จำนวนถังในระบบทั้งหมด</div>
                            <div class="text-[10px] md:text-xs text-blue-200 mt-1 font-medium">รวมทุกสถานะการใช้งาน</div>
                        </div>
                    </div>
                    <div class="text-4xl md:text-5xl font-black text-white">${totalTanks} <span class="text-base font-bold text-blue-200">ใบ</span></div>
                </div>

                <div class="grid grid-cols-2 lg:grid-cols-4 gap-3 md:gap-4">
                    <div class="bg-blue-50 rounded-2xl p-4 md:p-6 border border-blue-100 shadow-sm flex flex-col items-center justify-center transition-transform hover:scale-[1.02]">
                        <i class="fa-solid fa-box-open text-blue-400 text-3xl md:text-4xl mb-3"></i>
                        <span class="text-xs md:text-sm text-blue-800 font-bold mb-1 text-center">ถังเปล่าพร้อมใช้</span>
                        <div class="text-3xl md:text-4xl font-black text-blue-600">${counts.ready} <span class="text-sm font-bold opacity-70">ใบ</span></div>
                    </div>

                    <div class="bg-yellow-50 rounded-2xl p-4 md:p-6 border border-yellow-100 shadow-sm flex flex-col items-center justify-center transition-transform hover:scale-[1.02]">
                        <i class="fa-solid fa-cubes text-yellow-500 text-3xl md:text-4xl mb-3"></i>
                        <span class="text-xs md:text-sm text-yellow-800 font-bold mb-1 text-center">บรรจุแล้วรอขาย</span>
                        <div class="text-3xl md:text-4xl font-black text-yellow-600">${counts.stock} <span class="text-sm font-bold opacity-70">ใบ</span></div>
                    </div>

                    <div class="bg-green-50 rounded-2xl p-4 md:p-6 border border-green-100 shadow-sm flex flex-col items-center justify-center transition-transform hover:scale-[1.02]">
                        <i class="fa-solid fa-truck-fast text-green-500 text-3xl md:text-4xl mb-3"></i>
                        <span class="text-xs md:text-sm text-green-800 font-bold mb-1 text-center">ขายแล้วรอกลับ</span>
                        <div class="text-3xl md:text-4xl font-black text-green-600">${counts.customer} <span class="text-sm font-bold opacity-70">ใบ</span></div>
                    </div>

                    <div class="bg-gray-50 rounded-2xl p-4 md:p-6 border border-gray-200 shadow-sm flex flex-col items-center justify-center transition-transform hover:scale-[1.02]">
                        <i class="fa-solid fa-ban text-gray-400 text-3xl md:text-4xl mb-3"></i>
                        <span class="text-xs md:text-sm text-gray-700 font-bold mb-1 text-center">ถังไม่พร้อมใช้งาน</span>
                        <div class="text-3xl md:text-4xl font-black text-gray-600">${counts.inactive} <span class="text-sm font-bold opacity-70">ใบ</span></div>
                    </div>
                </div>

                <div class="mt-3 md:mt-4 bg-red-50 rounded-2xl p-5 md:p-6 border border-red-200 shadow-sm flex items-center justify-between transition-transform hover:scale-[1.01]">
                    <div class="flex items-center gap-4 md:gap-6">
                        <div class="bg-red-100 w-14 h-14 md:w-16 md:h-16 flex items-center justify-center rounded-full shrink-0">
                            <i class="fa-solid fa-triangle-exclamation text-red-500 text-2xl md:text-3xl"></i>
                        </div>
                        <div>
                            <div class="text-base md:text-lg text-red-800 font-black">คาดการณ์สูญหาย</div>
                            <div class="text-[10px] md:text-xs text-red-600 leading-snug mt-1 font-bold">
                                ถังเปล่า > ${window.lossThresholds.ready} วัน &bull; รอขาย > ${window.lossThresholds.stock} วัน &bull; รอกลับ > ${window.lossThresholds.customer} วัน
                            </div>
                        </div>
                    </div>
                    <div class="text-4xl md:text-5xl font-black text-red-600">${counts.loss} <span class="text-base font-bold text-red-400">ใบ</span></div>
                </div>
            `;
        }

        window.renderStockTable = () => {
            const tbody = document.getElementById('stock-table-body');
            const emptyState = document.getElementById('stock-empty-state');
            const emptyText = document.getElementById('stock-empty-text');
            
            if (!window.globalTanks || window.globalTanks.length === 0) {
                tbody.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyText.innerText = 'ยังไม่มีข้อมูลถังในระบบ';
                return;
            }

            const searchQuery = document.getElementById('search-stock-input').value.toUpperCase().trim();
            const statusFilter = document.getElementById('filter-stock-status').value;

            const filtered = window.globalTanks.filter(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);

                if (searchQuery && !tank.id.includes(searchQuery)) return false;
                if (statusFilter === 'all') return true;
                if (statusFilter === 'loss') return !!lossReason || tank.status === 'Loss';
                if (lossReason || tank.status === 'Loss') return false; 
                if (statusFilter === 'ready' && tank.status === 'Ready to Use') return true;
                if (statusFilter === 'stock' && tank.status === 'Stock') return true;
                if (statusFilter === 'customer' && tank.status === 'Customer') return true;
                if (statusFilter === 'inactive' && tank.status === 'Inactive') return true;

                return false;
            });

            if (filtered.length === 0) {
                tbody.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyText.innerText = 'ไม่พบข้อมูลตามเงื่อนไขที่ระบุ';
                return;
            }

            emptyState.classList.add('hidden');
            filtered.sort((a, b) => b.updatedAt - a.updatedAt);

            tbody.innerHTML = filtered.map(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);
                
                let badgeClass = 'bg-gray-100 text-gray-600 border-gray-200';
                let statusText = tank.status;
                let dayColor = 'text-gray-600';
                
                if (lossReason || tank.status === 'Loss') {
                    badgeClass = 'bg-red-50 text-red-700 border-red-200';
                    statusText = 'คาดการณ์สูญหาย';
                    dayColor = 'text-red-600';
                } else if (tank.status === 'Ready to Use') {
                    badgeClass = 'bg-blue-50 text-blue-700 border-blue-200';
                    statusText = 'ถังเปล่าพร้อมใช้';
                } else if (tank.status === 'Stock') {
                    badgeClass = 'bg-yellow-50 text-yellow-700 border-yellow-200';
                    statusText = 'บรรจุแล้วรอขาย';
                } else if (tank.status === 'Customer') {
                    badgeClass = 'bg-green-50 text-green-700 border-green-200';
                    statusText = 'ขายแล้วรอกลับ';
                } else if (tank.status === 'Inactive') {
                    badgeClass = 'bg-gray-100 text-gray-600 border-gray-200';
                    statusText = 'ถังไม่พร้อมใช้งาน';
                }

                return `
                    <tr class="hover:bg-gray-50/80 transition-colors">
                        <td class="p-4 font-black text-gray-800 whitespace-nowrap text-sm">${tank.id}</td>
                        <td class="p-4 whitespace-nowrap">
                            <span class="${badgeClass} border px-2.5 py-1 rounded-lg text-[10px] font-bold">${statusText}</span>
                            ${lossReason ? `<div class="text-[9px] text-red-500 mt-1 font-semibold leading-tight"><i class="fa-solid fa-circle-exclamation mr-1"></i>${lossReason}</div>` : ''}
                        </td>
                        <td class="p-4 whitespace-nowrap text-center">
                            <span class="text-[10px] text-purple-600 font-bold border border-purple-200 bg-purple-50 px-2.5 py-1 rounded-lg inline-block w-max mx-auto"><i class="fa-solid fa-arrows-spin mr-1"></i> ${tank.cycleCount || 0} รอบ</span>
                        </td>
                        <td class="p-4 text-[10px] text-gray-500 whitespace-nowrap">
                            <div class="font-bold text-gray-700">${new Date(tank.updatedAt).toLocaleDateString('th-TH', { year: '2-digit', month: 'short', day: 'numeric' })}</div>
                            <div>${new Date(tank.updatedAt).toLocaleTimeString('th-TH', { hour: '2-digit', minute: '2-digit' })} น.</div>
                        </td>
                        <td class="p-4 text-sm font-black ${dayColor} whitespace-nowrap text-center">
                            ${days} <span class="text-[10px] font-normal text-gray-400">วัน</span>
                        </td>
                    </tr>
                `;
            }).join('');
        };

        window.renderManageTable = () => {
            const tbody = document.getElementById('manage-table-body');
            const emptyState = document.getElementById('manage-empty-state');
            const emptyText = document.getElementById('manage-empty-text');
            
            if (!window.globalTanks || window.globalTanks.length === 0) {
                tbody.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyText.innerText = 'ยังไม่มีข้อมูลถังในระบบ';
                return;
            }

            const searchQuery = document.getElementById('search-manage-input').value.toUpperCase().trim();
            const statusFilter = document.getElementById('filter-manage-status').value;

            const filtered = window.globalTanks.filter(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);

                if (searchQuery && !tank.id.includes(searchQuery)) return false;
                if (statusFilter === 'all') return true;
                if (statusFilter === 'loss') return !!lossReason || tank.status === 'Loss';
                if (lossReason || tank.status === 'Loss') return false; 
                if (statusFilter === 'ready' && tank.status === 'Ready to Use') return true;
                if (statusFilter === 'stock' && tank.status === 'Stock') return true;
                if (statusFilter === 'customer' && tank.status === 'Customer') return true;
                if (statusFilter === 'inactive' && tank.status === 'Inactive') return true;

                return false;
            });

            if (filtered.length === 0) {
                tbody.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyText.innerText = 'ไม่พบข้อมูลตามเงื่อนไขที่ระบุ';
                return;
            }

            emptyState.classList.add('hidden');
            filtered.sort((a, b) => b.updatedAt - a.updatedAt);

            tbody.innerHTML = filtered.map(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);
                
                let badgeClass = 'bg-gray-100 text-gray-600 border-gray-200';
                let statusText = tank.status;
                
                if (lossReason || tank.status === 'Loss') {
                    badgeClass = 'bg-red-50 text-red-700 border-red-200';
                    statusText = 'คาดการณ์สูญหาย';
                } else if (tank.status === 'Ready to Use') {
                    badgeClass = 'bg-blue-50 text-blue-700 border-blue-200';
                    statusText = 'ถังเปล่าพร้อมใช้';
                } else if (tank.status === 'Stock') {
                    badgeClass = 'bg-yellow-50 text-yellow-700 border-yellow-200';
                    statusText = 'บรรจุแล้วรอขาย';
                } else if (tank.status === 'Customer') {
                    badgeClass = 'bg-green-50 text-green-700 border-green-200';
                    statusText = 'ขายแล้วรอกลับ';
                } else if (tank.status === 'Inactive') {
                    badgeClass = 'bg-gray-100 text-gray-600 border-gray-200';
                    statusText = 'ถังไม่พร้อมใช้งาน';
                }
                
                const customThreshStr = tank.customThresholds ? encodeURIComponent(JSON.stringify(tank.customThresholds)) : '';

                return `
                    <tr class="hover:bg-gray-50/80 transition-colors">
                        <td class="p-4 font-black text-gray-800 whitespace-nowrap text-sm">
                            ${tank.id}
                            ${tank.customThresholds ? `<br><span class="text-[9px] text-blue-500 font-normal border border-blue-200 bg-blue-50 px-1 rounded mt-1 inline-block">ตั้งค่าเฉพาะ</span>` : ''}
                        </td>
                        <td class="p-4 whitespace-nowrap">
                            <span class="${badgeClass} border px-2.5 py-1 rounded-lg text-[10px] font-bold">${statusText}</span>
                            ${lossReason ? `<div class="text-[9px] text-red-500 mt-1 font-semibold leading-tight"><i class="fa-solid fa-circle-exclamation mr-1"></i>${lossReason}</div>` : ''}
                        </td>
                        <td class="p-4 text-[10px] text-gray-500 whitespace-nowrap">
                            <div class="font-bold text-gray-700">${new Date(tank.updatedAt).toLocaleDateString('th-TH', { year: '2-digit', month: 'short', day: 'numeric' })}</div>
                            <div>${new Date(tank.updatedAt).toLocaleTimeString('th-TH', { hour: '2-digit', minute: '2-digit' })} น.</div>
                        </td>
                        <td class="p-4 whitespace-nowrap text-center">
                            <button onclick="openEditTankModal('${tank.id}', '${tank.status}', '${customThreshStr}')" class="bg-blue-50 text-blue-600 hover:bg-blue-100 hover:text-blue-700 px-4 py-2 rounded-lg text-xs font-bold transition-colors border border-blue-100 shadow-sm">
                                <i class="fa-solid fa-pen mr-1"></i> แก้ไขข้อมูล
                            </button>
                        </td>
                    </tr>
                `;
            }).join('');
        };

        window.toggleCustomThresholdInputs = () => {
            const isChecked = document.getElementById('edit-use-custom-thresholds').checked;
            const container = document.getElementById('custom-threshold-inputs');
            if (isChecked) {
                container.classList.remove('hidden');
            } else {
                container.classList.add('hidden');
            }
        };

        window.openEditTankModal = (tankId, currentStatus, customThresholdsStr) => {
            window.editingTankId = tankId;
            document.getElementById('edit-modal-tank-id').innerText = tankId;
            document.getElementById('edit-tank-status').value = currentStatus;
            
            const custom = customThresholdsStr ? JSON.parse(decodeURIComponent(customThresholdsStr)) : null;
            const useCheckbox = document.getElementById('edit-use-custom-thresholds');
            
            if (custom) {
                useCheckbox.checked = true;
                document.getElementById('edit-custom-ready').value = custom.ready || window.lossThresholds.ready;
                document.getElementById('edit-custom-stock').value = custom.stock || window.lossThresholds.stock;
                document.getElementById('edit-custom-customer').value = custom.customer || window.lossThresholds.customer;
            } else {
                useCheckbox.checked = false;
                document.getElementById('edit-custom-ready').value = window.lossThresholds.ready;
                document.getElementById('edit-custom-stock').value = window.lossThresholds.stock;
                document.getElementById('edit-custom-customer').value = window.lossThresholds.customer;
            }
            
            toggleCustomThresholdInputs();
            document.getElementById('edit-tank-modal').classList.remove('hidden');
        };

        window.closeEditTankModal = () => {
            document.getElementById('edit-tank-modal').classList.add('hidden');
            window.editingTankId = null;
        };

        window.submitEditTank = async () => {
            if (!window.editingTankId) return;
            const newStatus = document.getElementById('edit-tank-status').value;
            const tankId = window.editingTankId;
            const useCustom = document.getElementById('edit-use-custom-thresholds').checked;
            
            let customThresholds = null;
            let noteUpdateText = `ปรับสถานะเป็น: ${document.getElementById('edit-tank-status').options[document.getElementById('edit-tank-status').selectedIndex].text}`;
            
            if (useCustom) {
                customThresholds = {
                    ready: parseInt(document.getElementById('edit-custom-ready').value) || window.lossThresholds.ready,
                    stock: parseInt(document.getElementById('edit-custom-stock').value) || window.lossThresholds.stock,
                    customer: parseInt(document.getElementById('edit-custom-customer').value) || window.lossThresholds.customer
                };
                noteUpdateText += ` (ใช้การตั้งค่าสูญหายเฉพาะ)`;
            }
            
            Swal.fire({ title: 'กำลังบันทึกการแก้ไข...', allowOutsideClick: false, didOpen: () => { Swal.showLoading(); }});
            
            try {
                const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'tanks', tankId);
                const snap = await getDoc(docRef);
                let history = snap.exists() ? (snap.data().history || []) : [];
                
                history.push({
                    date: Date.now(),
                    action: 'แก้ไขข้อมูล (ระบบจัดการ)',
                    user: window.appUser,
                    note: noteUpdateText
                });

                await setDoc(docRef, { 
                    status: newStatus, 
                    updatedAt: Date.now(), 
                    history, 
                    customThresholds: customThresholds 
                }, { merge: true });
                
                window.closeEditTankModal();
                Swal.fire({ icon: 'success', title: 'อัปเดตข้อมูลสำเร็จ', timer: 1500, showConfirmButton: false });
            } catch (e) {
                console.error(e);
                Swal.fire('ข้อผิดพลาด', 'อัปเดตไม่สำเร็จ กรุณาลองใหม่', 'error');
            }
        };

        window.confirmDeleteTank = () => {
            const tankId = window.editingTankId;
            Swal.fire({
                title: 'ยืนยันการลบข้อมูล?',
                text: `คุณต้องการลบประวัติของถัง "${tankId}" ออกจากระบบใช่หรือไม่? (การกระทำนี้ไม่สามารถกู้คืนได้)`,
                icon: 'warning',
                showCancelButton: true,
                confirmButtonColor: '#ef4444',
                cancelButtonColor: '#9ca3af',
                confirmButtonText: '<i class="fa-solid fa-trash-can mr-1"></i> ลบข้อมูลถาวร',
                cancelButtonText: 'ยกเลิก'
            }).then(async (result) => {
                if (result.isConfirmed) {
                    try {
                        Swal.fire({ title: 'กำลังลบข้อมูล...', allowOutsideClick: false, didOpen: () => { Swal.showLoading(); }});
                        await deleteDoc(doc(db, 'artifacts', appId, 'public', 'data', 'tanks', tankId));
                        window.closeEditTankModal();
                        Swal.fire({ icon: 'success', title: 'ลบสำเร็จ!', text: `ข้อมูลถัง ${tankId} ถูกลบแล้ว`, timer: 1500, showConfirmButton: false });
                    } catch (error) {
                        console.error(error);
                        Swal.fire('เกิดข้อผิดพลาด', 'ไม่สามารถลบข้อมูลได้ กรุณาลองใหม่อีกครั้ง', 'error');
                    }
                }
            });
        };

        window.openSettingsModal = () => {
            document.getElementById('setting-days-ready').value = window.lossThresholds.ready;
            document.getElementById('setting-days-stock').value = window.lossThresholds.stock;
            document.getElementById('setting-days-customer').value = window.lossThresholds.customer;
            document.getElementById('settings-modal').classList.remove('hidden');
        };

        window.closeSettingsModal = () => {
            document.getElementById('settings-modal').classList.add('hidden');
        };

        window.submitSettings = async () => {
            const r = parseInt(document.getElementById('setting-days-ready').value) || 30;
            const s = parseInt(document.getElementById('setting-days-stock').value) || 45;
            const c = parseInt(document.getElementById('setting-days-customer').value) || 7;
            
            Swal.fire({ title: 'กำลังบันทึกการตั้งค่า...', allowOutsideClick: false, didOpen: () => { Swal.showLoading(); }});
            
            try {
                const configRef = doc(db, 'artifacts', appId, 'public', 'data', 'settings', 'thresholds');
                await setDoc(configRef, { ready: r, stock: s, customer: c });
                
                window.lossThresholds = { ready: r, stock: s, customer: c };
                
                window.closeSettingsModal();
                Swal.fire({ icon: 'success', title: 'ตั้งค่าสำเร็จ', timer: 1500, showConfirmButton: false });
                
                renderDashboard();
                if(document.getElementById('view-stock').classList.contains('active')) renderStockTable();
                if(document.getElementById('view-manage').classList.contains('active')) renderManageTable();
                
            } catch(e) {
                console.error(e);
                Swal.fire('ข้อผิดพลาด', 'ไม่สามารถบันทึกการตั้งค่าได้', 'error');
            }
        };

        // --- SCANNER LOGIC ---
        function showCameraError() {
            document.getElementById('camera-error-text').classList.remove('hidden');
            document.getElementById('camera-error-text').innerHTML = `<i class="fa-solid fa-triangle-exclamation mr-1"></i> ไม่พบกล้องที่ใช้งานได้`;
            document.getElementById('reader').innerHTML = '<div class="text-gray-500 text-center p-8 pt-12 text-sm font-bold"><i class="fa-solid fa-camera-rotate text-3xl mb-3 text-gray-400"></i><br>กล้องไม่พร้อมใช้งาน<br><span class="text-xs font-normal">กรุณาสแกนจากรูปภาพหรือกรอกรหัส</span></div>';
        }

        async function startScanner() {
            if (!html5QrCode) html5QrCode = new Html5Qrcode("reader");
            if (html5QrCode.isScanning) return;

            const config = { fps: 15, qrbox: { width: 250, height: 250 } };
            
            Html5Qrcode.getCameras().then(async devices => {
                if (devices && devices.length > 0) {
                    try {
                        await html5QrCode.start({ facingMode: "environment" }, config, onScanSuccess, () => {});
                    } catch (err) {
                        try {
                            await html5QrCode.start(devices[0].id, config, onScanSuccess, () => {});
                        } catch (fallbackErr) {
                            showCameraError();
                        }
                    }
                } else {
                    showCameraError();
                }
            }).catch(err => {
                showCameraError();
            });
        }

        async function stopScanner() {
            if (html5QrCode && html5QrCode.isScanning) {
                await html5QrCode.stop().catch(err => console.error(err));
            }
        }

        function onScanSuccess(decodedText) {
            stopScanner();
            const audio = new Audio('https://actions.google.com/sounds/v1/ui/button_click.ogg');
            audio.play().catch(e=>{});
            
            const tankId = decodedText.trim().toUpperCase();
            document.getElementById('manual-tank-id').value = tankId;
            
            Swal.fire({ 
                icon: 'success', 
                title: 'สแกนสำเร็จ', 
                text: 'กรุณาตรวจสอบรหัสถังและกดปุ่ม "ยืนยัน" เพื่อบันทึก', 
                timer: 2000, 
                showConfirmButton: false 
            });
        }

        window.handleFileUpload = (event) => {
            const file = event.target.files[0];
            if (!file) return;
            if (!html5QrCode) html5QrCode = new Html5Qrcode("reader");

            Swal.fire({ title: 'กำลังถอดรหัสรูปภาพ...', allowOutsideClick: false, didOpen: () => Swal.showLoading() });

            html5QrCode.scanFile(file, true)
                .then(text => { 
                    Swal.close(); 
                    
                    const tankId = text.trim().toUpperCase();
                    document.getElementById('manual-tank-id').value = tankId;
                    event.target.value = ''; 
                    
                    Swal.fire({ 
                        icon: 'success', 
                        title: 'ถอดรหัสภาพสำเร็จ', 
                        text: 'กรุณาตรวจสอบรหัสถังและกดปุ่ม "ยืนยัน" เพื่อบันทึก', 
                        timer: 2000, 
                        showConfirmButton: false 
                    });
                })
                .catch(err => { 
                    Swal.fire({ icon: 'error', title: 'ไม่พบ QR Code', text: 'รูปภาพอาจไม่ชัด กรุณาลองใหม่หรือสแกนสด' }); 
                    event.target.value = ''; 
                });
        };

        window.processScannedTank = (tankId) => {
            if (!window.currentUser || !window.appUser) {
                Swal.fire({ icon: 'info', title: 'รอสักครู่', text: 'กำลังตรวจสอบสิทธิ์การใช้งาน...' });
                return;
            }
            const action = document.getElementById('current-action').value;
            
            const existingTank = window.globalTanks.find(t => t.id === tankId);
            let skippedStep = null; // ตัวแปรสำหรับเก็บชื่อกระบวนการที่ถูกข้าม

            if (existingTank) {
                let isDuplicate = false;
                
                if (action === 'receive' && existingTank.status === 'Ready to Use') isDuplicate = true;
                if (action === 'pack' && existingTank.status === 'Stock') isDuplicate = true;
                if (action === 'dispatch' && existingTank.status === 'Customer') isDuplicate = true;
                
                if (isDuplicate) {
                    Swal.fire({
                        icon: 'warning',
                        title: 'ข้อมูลซ้ำซ้อน',
                        text: `ถังรหัส ${tankId} อยู่ในกระบวนการนี้อยู่แล้ว`,
                        confirmButtonColor: '#2563eb'
                    }).then(() => {
                        document.getElementById('manual-tank-id').value = '';
                        if (document.getElementById('view-scan').classList.contains('active')) startScanner();
                    });
                    return;
                }

                if (existingTank.status === 'Inactive' && (action === 'pack' || action === 'dispatch')) {
                    Swal.fire({
                        icon: 'error',
                        title: 'ไม่อนุญาตให้ทำรายการ',
                        text: `ถังรหัส ${tankId} มีสถานะ "ไม่พร้อมใช้งาน" (ชำรุด) ไม่สามารถนำไปบรรจุหรือจ่ายออกได้`,
                        confirmButtonColor: '#ef4444'
                    }).then(() => {
                        document.getElementById('manual-tank-id').value = '';
                        if (document.getElementById('view-scan').classList.contains('active')) startScanner();
                    });
                    return; 
                }

                // --- ตรวจสอบการข้ามกระบวนการ (Skip Process) ---
                if (existingTank.status === 'Ready to Use' && action === 'dispatch') skippedStep = 'บรรจุ';
                if (existingTank.status === 'Stock' && action === 'receive') skippedStep = 'จ่ายออก';
                if (existingTank.status === 'Customer' && action === 'pack') skippedStep = 'รับเข้า';

            } else {
                // กรณีถังใหม่เอี่ยม ไม่มีในระบบ
                if (action === 'pack') skippedStep = 'รับเข้า';
                if (action === 'dispatch') skippedStep = 'รับเข้าและบรรจุ';
            }

            const openReceiveModal = () => {
                pendingTankId = tankId;
                document.getElementById('modal-tank-id').innerText = `${tankId}`;
                document.getElementById('cond-note').value = '';
                document.querySelectorAll('input[type=radio][value="ดี"]').forEach(radio => radio.checked = true);
                document.querySelectorAll('input[type=radio][value="พร้อมนำไปบรรจุ"]').forEach(radio => radio.checked = true);
                document.getElementById('condition-modal').classList.remove('hidden');
            };

            const resetScannerUI = () => {
                document.getElementById('manual-tank-id').value = '';
                if (document.getElementById('view-scan').classList.contains('active')) startScanner();
            };

            if (action === 'receive') {
                window.pendingSkippedStep = skippedStep; // เก็บไว้ใช้ตอนกดยืนยันใน Modal
                if (skippedStep) {
                    Swal.fire({
                        title: 'พบการข้ามกระบวนการ!',
                        html: `ถัง <b>${tankId}</b> ข้ามกระบวนการ <b class="text-red-500">"${skippedStep}"</b><br>คุณต้องการดำเนินการรับเข้าต่อหรือไม่?`,
                        icon: 'warning',
                        showCancelButton: true,
                        confirmButtonColor: '#f59e0b',
                        cancelButtonColor: '#9ca3af',
                        confirmButtonText: 'ยืนยัน (ข้ามขั้นตอน)',
                        cancelButtonText: 'ยกเลิก'
                    }).then((result) => {
                        if (result.isConfirmed) {
                            openReceiveModal();
                        } else {
                            resetScannerUI();
                        }
                    });
                } else {
                    openReceiveModal();
                }
            } else {
                let actionName = action === 'pack' ? 'บรรจุ' : 'จ่ายออก';
                
                let swalConfig = {
                    title: 'ยืนยันการบันทึก?',
                    html: `ต้องการอัปเดตถัง <b>${tankId}</b> เป็นสถานะ "${actionName}" ใช่หรือไม่?`,
                    icon: 'question',
                    showCancelButton: true,
                    confirmButtonColor: '#2563eb',
                    cancelButtonColor: '#9ca3af',
                    confirmButtonText: 'ยืนยัน',
                    cancelButtonText: 'ยกเลิก'
                };

                if (skippedStep) {
                    swalConfig.title = 'พบการข้ามกระบวนการ!';
                    swalConfig.html = `<div class="mb-3 text-red-500 font-bold bg-red-50 p-2 rounded-lg border border-red-200">⚠️ ข้ามขั้นตอน "${skippedStep}"</div>ต้องการอัปเดตถัง <b>${tankId}</b> เป็นสถานะ <b>"${actionName}"</b> ใช่หรือไม่?`;
                    swalConfig.icon = 'warning';
                    swalConfig.confirmButtonColor = '#f59e0b';
                    swalConfig.confirmButtonText = 'ยืนยัน (ข้ามขั้นตอน)';
                }

                Swal.fire(swalConfig).then((result) => {
                    if (result.isConfirmed) {
                        executeTankUpdate(tankId, action, { skipped: skippedStep });
                    } else {
                        resetScannerUI();
                    }
                });
            }
        };

        window.executeTankUpdate = async (tankId, actionType, conditions = null) => {
            try {
                let newStatus = '', actionText = '', finalNote = '';
                
                if (actionType === 'receive') {
                    if (conditions?.isBad) { newStatus = 'Inactive'; actionText = 'รับเข้า (ชำรุด/ไม่พร้อม)'; finalNote = conditions.note; }
                    else { newStatus = 'Ready to Use'; actionText = 'รับเข้า (พร้อมใช้)'; finalNote = conditions?.note || ''; }
                } else if (actionType === 'pack') { 
                    newStatus = 'Stock'; actionText = 'บรรจุ'; 
                    if (conditions?.skipped) finalNote = `[ข้ามขั้นตอน: ${conditions.skipped}]`;
                } else if (actionType === 'dispatch') { 
                    newStatus = 'Customer'; actionText = 'จ่ายออก'; 
                    if (conditions?.skipped) finalNote = `[ข้ามขั้นตอน: ${conditions.skipped}]`;
                }

                Swal.fire({
                    title: 'กำลังบันทึกข้อมูล...',
                    text: 'กรุณารอสักครู่',
                    allowOutsideClick: false,
                    showConfirmButton: false,
                    didOpen: () => {
                        Swal.showLoading();
                    }
                });

                const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'tanks', tankId);
                const snap = await getDoc(docRef);
                const now = Date.now();
                
                // ดึงข้อมูลเดิมมาเพื่อคำนวณรอบ
                let tankData = snap.exists() ? snap.data() : null;
                let history = tankData ? (tankData.history || []) : [];
                let cycleCount = tankData ? (tankData.cycleCount || 0) : 0;

                // --- ระบบตรวจสอบการครบรอบ (Cycle Increment) ---
                // ถ้ารับเข้า แล้วสถานะเดิมคือ 'Customer' (ขายแล้วรอกลับ) ให้นับเพิ่ม 1 รอบทันที
                if (actionType === 'receive' && tankData && tankData.status === 'Customer') {
                    cycleCount += 1;
                    let cycleText = `[จบรอบที่ ${cycleCount}]`;
                    finalNote = finalNote ? `${cycleText} ${finalNote}` : cycleText;
                }

                const historyEntry = { date: now, action: actionText, user: window.appUser, note: finalNote };
                history.push(historyEntry);

                await setDoc(docRef, { 
                    status: newStatus, 
                    updatedAt: now, 
                    note: finalNote, 
                    history,
                    cycleCount: cycleCount // บันทึกรอบลงฐานข้อมูล
                }, { merge: true });

                document.getElementById('manual-tank-id').value = '';

                Swal.fire({ icon: 'success', title: 'บันทึกสำเร็จ!', text: `อัปเดตถัง ${tankId} เป็นสถานะ: ${newStatus}`, timer: 1500, showConfirmButton: false })
                    .then(() => { if (document.getElementById('view-scan').classList.contains('active')) startScanner(); });

            } catch (error) {
                console.error(error);
                Swal.fire({ icon: 'error', title: 'บันทึกล้มเหลว', text: 'กรุณาตรวจสอบการเชื่อมต่ออินเทอร์เน็ต' });
            }
        };

        // --- Navigation ---
        window.switchTab = (id) => {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
            document.getElementById(`view-${id}`).classList.add('active');
            
            document.querySelectorAll('.nav-btn-mobile').forEach(btn => btn.classList.replace('text-blue-600', 'text-gray-400'));
            const mobBtn = document.getElementById(`nav-mobile-${id}`);
            if(mobBtn) mobBtn.classList.replace('text-gray-400', 'text-blue-600');
            
            document.querySelectorAll('.nav-btn-desktop').forEach(btn => {
                btn.classList.remove('bg-blue-50', 'text-blue-600');
                btn.classList.add('text-gray-500', 'hover:bg-gray-50');
            });
            const deskBtn = document.getElementById(`nav-desktop-${id}`);
            if(deskBtn) {
                deskBtn.classList.remove('text-gray-500', 'hover:bg-gray-50');
                deskBtn.classList.add('bg-blue-50', 'text-blue-600');
            }
            
            if (id === 'scan') startScanner();
            else stopScanner();

            if (id === 'dashboard') renderDashboard();
            if (id === 'stock') renderStockTable();
            if (id === 'manage') renderManageTable();
            if (id === 'search') renderSearchTable();
            if (id === 'label') renderLabelPreview();
        };

        window.setScanAction = (action) => {
            document.getElementById('current-action').value = action;
            document.querySelectorAll('.action-btn').forEach(btn => {
                btn.classList.replace('border-blue-500', 'border-transparent');
                btn.classList.replace('text-blue-800', 'text-gray-500');
                btn.classList.replace('bg-blue-100', 'bg-gray-50');
            });
            const active = document.getElementById(`btn-action-${action}`);
            if(active) {
                active.classList.replace('border-transparent', 'border-blue-500');
                active.classList.replace('text-gray-500', 'text-blue-800');
                active.classList.replace('bg-gray-50', 'bg-blue-100');
            }
        };

        window.closeConditionModal = () => {
            document.getElementById('condition-modal').classList.add('hidden');
            if (document.getElementById('view-scan').classList.contains('active')) startScanner();
        };

        window.submitTankCondition = () => {
            const v = document.querySelector('input[name="cond-valve"]:checked').value;
            const s = document.querySelector('input[name="cond-struct"]:checked').value;
            const b = document.querySelector('input[name="cond-base"]:checked').value;
            const r = document.querySelector('input[name="cond-ready"]:checked').value;
            const n = document.getElementById('cond-note').value;
            
            const bad = (r === 'ไม่พร้อมนำไปบรรจุ');
            
            let noteStr = `[วาล์ว:${v}, โครง:${s}, ฐาน:${b}, สถานะ:${r}] ${n}`;
            if (window.pendingSkippedStep) {
                noteStr = `[ข้ามขั้นตอน: ${window.pendingSkippedStep}] ` + noteStr;
            }
            
            Swal.fire({
                title: 'ยืนยันการบันทึกข้อมูล?',
                text: "โปรดตรวจสอบความถูกต้องของข้อมูลสภาพถังก่อนบันทึก",
                icon: 'question',
                showCancelButton: true,
                confirmButtonColor: '#2563eb',
                cancelButtonColor: '#9ca3af',
                confirmButtonText: 'บันทึกข้อมูล',
                cancelButtonText: 'ยกเลิก'
            }).then((result) => {
                if (result.isConfirmed) {
                    executeTankUpdate(pendingTankId, 'receive', { isBad: bad, note: noteStr });
                    document.getElementById('condition-modal').classList.add('hidden');
                }
            });
        };

        window.handleManualSubmit = () => {
            const val = document.getElementById('manual-tank-id').value.trim().toUpperCase();
            if(val) { 
                processScannedTank(val); 
            } else {
                Swal.fire({ icon: 'warning', title: 'แจ้งเตือน', text: 'กรุณากรอกรหัสถังก่อนกดยืนยัน', confirmButtonColor: '#2563eb' });
            }
        };

        // --- RENDER SEARCH/HISTORY TABLE ---
        window.renderSearchTable = () => {
            const tbody = document.getElementById('search-table-body');
            const emptyState = document.getElementById('search-empty-state');
            const emptyText = document.getElementById('search-empty-text');
            
            if (!window.globalTanks || window.globalTanks.length === 0) {
                tbody.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyText.innerText = 'ยังไม่มีข้อมูลถังในระบบ';
                return;
            }

            const searchQuery = document.getElementById('search-history-input').value.toUpperCase().trim();
            const statusFilter = document.getElementById('filter-history-status').value;

            const filtered = window.globalTanks.filter(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);

                if (searchQuery && !tank.id.includes(searchQuery)) return false;
                if (statusFilter === 'all') return true;
                if (statusFilter === 'loss') return !!lossReason || tank.status === 'Loss';
                if (lossReason || tank.status === 'Loss') return false; 
                if (statusFilter === 'ready' && tank.status === 'Ready to Use') return true;
                if (statusFilter === 'stock' && tank.status === 'Stock') return true;
                if (statusFilter === 'customer' && tank.status === 'Customer') return true;
                if (statusFilter === 'inactive' && tank.status === 'Inactive') return true;

                return false;
            });

            if (filtered.length === 0) {
                tbody.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyText.innerText = 'ไม่พบข้อมูลตามเงื่อนไขที่ระบุ';
                return;
            }

            emptyState.classList.add('hidden');
            filtered.sort((a, b) => b.updatedAt - a.updatedAt);

            tbody.innerHTML = filtered.map(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);
                
                let badgeClass = 'bg-gray-100 text-gray-600 border-gray-200';
                let statusText = tank.status;
                
                if (lossReason || tank.status === 'Loss') {
                    badgeClass = 'bg-red-50 text-red-700 border-red-200';
                    statusText = 'คาดการณ์สูญหาย';
                } else if (tank.status === 'Ready to Use') {
                    badgeClass = 'bg-blue-50 text-blue-700 border-blue-200';
                    statusText = 'ถังเปล่าพร้อมใช้';
                } else if (tank.status === 'Stock') {
                    badgeClass = 'bg-yellow-50 text-yellow-700 border-yellow-200';
                    statusText = 'บรรจุแล้วรอขาย';
                } else if (tank.status === 'Customer') {
                    badgeClass = 'bg-green-50 text-green-700 border-green-200';
                    statusText = 'ขายแล้วรอกลับ';
                } else if (tank.status === 'Inactive') {
                    badgeClass = 'bg-gray-100 text-gray-600 border-gray-200';
                    statusText = 'ถังไม่พร้อมใช้งาน';
                }

                return `
                    <tr class="hover:bg-gray-50/80 transition-colors cursor-pointer" onclick="viewTankHistory('${tank.id}')">
                        <td class="p-4 font-black text-gray-800 whitespace-nowrap text-sm">
                            ${tank.id}
                            <div class="mt-1 flex flex-col items-start gap-1">
                                <span class="text-[9px] text-purple-600 font-bold border border-purple-200 bg-purple-50 px-1.5 py-0.5 rounded flex items-center w-max"><i class="fa-solid fa-arrows-spin mr-1"></i> รอบใช้งาน: ${tank.cycleCount || 0}</span>
                            </div>
                        </td>
                        <td class="p-4 whitespace-nowrap">
                            <span class="${badgeClass} border px-2.5 py-1 rounded-lg text-[10px] font-bold">${statusText}</span>
                        </td>
                        <td class="p-4 text-[10px] text-gray-500 whitespace-nowrap">
                            <div class="font-bold text-gray-700">${new Date(tank.updatedAt).toLocaleDateString('th-TH', { year: '2-digit', month: 'short', day: 'numeric' })}</div>
                            <div>${new Date(tank.updatedAt).toLocaleTimeString('th-TH', { hour: '2-digit', minute: '2-digit' })} น.</div>
                        </td>
                        <td class="p-4 whitespace-nowrap text-center">
                            <button class="bg-gray-100 text-gray-600 hover:bg-blue-50 hover:text-blue-700 px-4 py-2 rounded-lg text-xs font-bold transition-colors border border-gray-200 shadow-sm">
                                <i class="fa-solid fa-list mr-1"></i> ดูประวัติ
                            </button>
                        </td>
                    </tr>
                `;
            }).join('');
        };

        // --- HISTORY MODAL LOGIC ---
        window.viewTankHistory = (tankId) => {
            const tank = window.globalTanks.find(t => t.id === tankId);
            if (!tank) return;

            const sortedHistory = (tank.history || []).slice().sort((a, b) => b.date - a.date);
            
            const actionCounts = sortedHistory.reduce((acc, curr) => {
                const baseAction = curr.action.split(' ')[0];
                acc[baseAction] = (acc[baseAction] || 0) + 1;
                return acc;
            }, {});
            
            const countsHtml = Object.entries(actionCounts).map(([action, count]) => 
                `<span class="bg-blue-50 text-blue-700 px-2 py-1 rounded-lg text-[10px] font-bold border border-blue-100 mr-2 mb-2 inline-block">${action}: ${count}</span>`
            ).join('');

            let historyHtml = '<div class="text-center py-6 text-gray-400 text-sm font-bold">ไม่มีข้อมูลประวัติ</div>';
            if (sortedHistory.length > 0) {
                historyHtml = sortedHistory.map((h, idx) => `
                    <div class="flex justify-between items-start border-b border-gray-200 pb-3 mb-3 last:border-0 last:pb-0 last:mb-0 relative">
                        ${idx === 0 ? '<div class="absolute -left-4 top-1.5 w-1.5 h-[calc(100%-12px)] bg-blue-500 rounded-full"></div><div class="pl-1">' : '<div>'}
                            <div class="font-bold ${idx === 0 ? 'text-blue-700' : 'text-gray-700'} text-xs">
                                ${h.action} 
                                ${idx === 0 ? '<span class="bg-blue-100 text-blue-600 text-[8px] px-1.5 py-0.5 rounded ml-1">ล่าสุด</span>' : ''}
                            </div>
                            ${h.note ? `<div class="text-[10px] text-gray-500 italic mt-1 leading-snug">${h.note}</div>` : ''}
                            <div class="text-[9px] text-gray-400 mt-1">โดย: <span class="font-bold">${h.user}</span></div>
                        ${idx === 0 ? '</div>' : '</div>'}
                        <div class="text-right shrink-0 ml-2">
                            <div class="text-[10px] font-bold text-gray-600">${new Date(h.date).toLocaleDateString('th-TH', {year: '2-digit', month: 'short', day: 'numeric'})}</div>
                            <div class="text-[9px] text-gray-400">${new Date(h.date).toLocaleTimeString('th-TH', {hour: '2-digit', minute: '2-digit'})} น.</div>
                        </div>
                    </div>
                `).join('');
            }

            const contentHtml = `
                <div class="mb-5 border-b border-gray-100 pb-5">
                    <span class="font-black text-gray-800 text-2xl block mb-3">${tank.id}</span>
                    <div class="flex items-center flex-wrap gap-2 mb-3">
                        <span class="text-xs font-bold px-3 py-1.5 bg-purple-50 text-purple-700 rounded-lg border border-purple-200 inline-block">
                            <i class="fa-solid fa-arrows-spin mr-1"></i> ใช้งานไปแล้ว: ${tank.cycleCount || 0} รอบ
                        </span>
                        <span class="text-xs font-bold px-3 py-1.5 bg-gray-100 rounded-lg text-gray-600 border border-gray-200 inline-block">
                            สถานะล่าสุด: <span class="text-blue-600">${tank.status}</span>
                        </span>
                    </div>
                    <div class="flex flex-wrap mb-3">${countsHtml}</div>
                </div>
                <div class="bg-gray-50 p-5 rounded-2xl border border-gray-100">
                    <div class="font-bold text-gray-700 mb-4 flex justify-between items-center border-b border-gray-200 pb-3">
                        <span class="text-xs uppercase tracking-wider"><i class="fa-solid fa-list-ul mr-1 text-gray-400"></i> ลำดับเหตุการณ์ (${sortedHistory.length})</span>
                    </div>
                    <div>
                        ${historyHtml}
                    </div>
                </div>
            `;

            document.getElementById('history-modal-content').innerHTML = contentHtml;
            document.getElementById('history-modal').classList.remove('hidden');
        };

        window.closeHistoryModal = () => {
            document.getElementById('history-modal').classList.add('hidden');
        };

        // --- EXPORT TO EXCEL LOGIC ---
        window.exportToExcel = () => {
            if (!window.globalTanks || window.globalTanks.length === 0) {
                Swal.fire({ icon: 'warning', title: 'ไม่มีข้อมูล', text: 'ไม่พบข้อมูลสำหรับส่งออก', confirmButtonColor: '#2563eb' });
                return;
            }

            const searchQuery = document.getElementById('search-history-input').value.toUpperCase().trim();
            const statusFilter = document.getElementById('filter-history-status').value;

            const filtered = window.globalTanks.filter(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);

                if (searchQuery && !tank.id.includes(searchQuery)) return false;
                if (statusFilter === 'all') return true;
                if (statusFilter === 'loss') return !!lossReason || tank.status === 'Loss';
                if (lossReason || tank.status === 'Loss') return false; 
                if (statusFilter === 'ready' && tank.status === 'Ready to Use') return true;
                if (statusFilter === 'stock' && tank.status === 'Stock') return true;
                if (statusFilter === 'customer' && tank.status === 'Customer') return true;
                if (statusFilter === 'inactive' && tank.status === 'Inactive') return true;

                return false;
            });

            if (filtered.length === 0) {
                Swal.fire({ icon: 'warning', title: 'ไม่มีข้อมูล', text: 'ไม่พบข้อมูลตามเงื่อนไขที่ระบุ', confirmButtonColor: '#2563eb' });
                return;
            }

            const excelData = [];

            filtered.forEach(tank => {
                const days = calculateDays(tank.updatedAt);
                const lossReason = getExpectedLossInfo(tank.status, days, tank.customThresholds);
                
                let statusText = tank.status;
                if (lossReason || tank.status === 'Loss') statusText = 'คาดการณ์สูญหาย';
                else if (tank.status === 'Ready to Use') statusText = 'ถังเปล่าพร้อมใช้';
                else if (tank.status === 'Stock') statusText = 'บรรจุแล้วรอขาย';
                else if (tank.status === 'Customer') statusText = 'ขายแล้วรอกลับ';
                else if (tank.status === 'Inactive') statusText = 'ถังไม่พร้อมใช้งาน';

                const sortedHistory = (tank.history || []).slice().sort((a, b) => b.date - a.date);

                if (sortedHistory.length === 0) {
                    excelData.push({
                        'รหัสถัง': tank.id,
                        'สถานะปัจจุบันของถัง': statusText,
                        'รอบการใช้งาน': tank.cycleCount || 0,
                        'จำนวนวันคงค้าง': days,
                        'กระบวนการที่ทำ': '-',
                        'วันที่ทำรายการ': '-',
                        'เวลาที่ทำรายการ': '-',
                        'ผู้ทำรายการ': '-',
                        'บันทึกเพิ่มเติม': '-',
                        'หมายเหตุสถานะ': lossReason || '-'
                    });
                } else {
                    sortedHistory.forEach((h, index) => {
                        excelData.push({
                            'รหัสถัง': tank.id,
                            'สถานะปัจจุบันของถัง': statusText,
                            'รอบการใช้งาน': tank.cycleCount || 0,
                            'จำนวนวันคงค้าง': days,
                            'กระบวนการที่ทำ': h.action,
                            'วันที่ทำรายการ': new Date(h.date).toLocaleDateString('th-TH', { year: 'numeric', month: '2-digit', day: '2-digit' }),
                            'เวลาที่ทำรายการ': new Date(h.date).toLocaleTimeString('th-TH', { hour: '2-digit', minute: '2-digit' }) + ' น.',
                            'ผู้ทำรายการ': h.user,
                            'บันทึกเพิ่มเติม': h.note || '-',
                            'หมายเหตุสถานะ': lossReason || '-'
                        });
                    });
                }
            });

            try {
                const worksheet = XLSX.utils.json_to_sheet(excelData);
                const workbook = XLSX.utils.book_new();
                XLSX.utils.book_append_sheet(workbook, worksheet, "Tank Data");
                
                const dateStr = new Date().toISOString().slice(0, 10);
                XLSX.writeFile(workbook, `PK_Tank_Report_${dateStr}.xlsx`);
                
                Swal.fire({ icon: 'success', title: 'สำเร็จ', text: 'ดาวน์โหลดไฟล์ Excel เรียบร้อยแล้ว', timer: 1500, showConfirmButton: false });
            } catch (error) {
                console.error("Export error:", error);
                Swal.fire({ icon: 'error', title: 'เกิดข้อผิดพลาด', text: 'ไม่สามารถสร้างไฟล์ Excel ได้', confirmButtonColor: '#2563eb' });
            }
        };

    </script>
</body>
</html>

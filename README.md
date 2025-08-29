# counter-sales-knowledge-base
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Counter Sales Knowledge Base - Stevens Parts</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #2c3e50 0%, #3498db 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            background: white;
            margin-top: 20px;
            margin-bottom: 20px;
            border-radius: 15px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            padding: 25px 0;
            border-bottom: 4px solid #3498db;
            background: linear-gradient(45deg, #f8f9fa, #e9ecef);
            border-radius: 10px;
        }
        
        .header h1 {
            color: #2c3e50;
            font-size: 2.8em;
            margin-bottom: 10px;
            font-weight: 800;
        }
        
        .header .subtitle {
            color: #7f8c8d;
            font-size: 1.3em;
            margin-bottom: 20px;
            font-weight: 500;
        }
        
        .stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            flex-wrap: wrap;
        }
        
        .stat-item {
            text-align: center;
            background: linear-gradient(45deg, #3498db, #2980b9);
            color: white;
            padding: 20px 30px;
            border-radius: 60px;
            font-weight: bold;
            box-shadow: 0 8px 20px rgba(52, 152, 219, 0.4);
        }
        
        .stat-number {
            font-size: 2.2em;
            display: block;
            font-weight: 900;
        }
        
        .quick-tools {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .tool-card {
            background: linear-gradient(45deg, #ecf0f1, #bdc3c7);
            padding: 25px;
            border-radius: 15px;
            border-left: 6px solid #3498db;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }
        
        .tool-card h3 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 1.4em;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .filters {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 30px;
            padding: 25px;
            background: #f8f9fa;
            border-radius: 15px;
            border-left: 6px solid #3498db;
        }
        
        .filter-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        
        .filter-group label {
            font-weight: bold;
            color: #2c3e50;
            font-size: 0.95em;
        }
        
        .filter-group select, .filter-group input {
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            min-width: 180px;
            transition: all 0.3s ease;
        }
        
        .filter-group select:focus, .filter-group input:focus {
            border-color: #3498db;
            outline: none;
            box-shadow: 0 0 10px rgba(52, 152, 219, 0.3);
        }
        
        .search-box {
            flex: 1;
            min-width: 250px;
        }
        
        .diagnostic-section {
            background: linear-gradient(45deg, #e8f6fd, #d5f0fc);
            padding: 25px;
            margin-bottom: 30px;
            border-radius: 15px;
            border-left: 6px solid #3498db;
        }
        
        .diagnostic-title {
            color: #2980b9;
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .customer-questions {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 15px;
        }
        
        .customer-question {
            background: white;
            padding: 20px;
            border-radius: 12px;
            border: 2px solid #ecf0f1;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        
        .customer-question:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
            border-color: #3498db;
        }
        
        .customer-question.active {
            background: #3498db;
            color: white;
            border-color: #2980b9;
        }
        
        .question-title {
            font-weight: bold;
            margin-bottom: 8px;
            font-size: 1.1em;
        }
        
        .question-desc {
            font-size: 0.95em;
            color: #7f8c8d;
            line-height: 1.5;
        }
        
        .customer-question.active .question-desc {
            color: #ecf0f1;
        }
        
        .table-container {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 8px 30px rgba(0,0,0,0.15);
            margin-bottom: 30px;
        }
        
        .table-header {
            background: linear-gradient(45deg, #3498db, #2980b9);
            color: white;
            padding: 20px 25px;
            font-size: 1.3em;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #ecf0f1;
        }
        
        th {
            background: #f8f9fa;
            font-weight: bold;
            color: #2c3e50;
            position: sticky;
            top: 0;
            z-index: 10;
        }
        
        tbody tr:hover {
            background: #f8f9fa;
        }
        
        .part-number {
            font-weight: bold;
            color: #3498db;
            font-size: 1.1em;
        }
        
        .brand-badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: bold;
            text-transform: uppercase;
        }
        
        .brand-whirlpool { background: #e3f2fd; color: #1976d2; }
        .brand-ge { background: #fff3e0; color: #f57c00; }
        .brand-lg { background: #fce4ec; color: #c2185b; }
        .brand-samsung { background: #e8f5e8; color: #388e3c; }
        
        .stock-indicator {
            font-weight: bold;
            padding: 5px 10px;
            border-radius: 15px;
            text-align: center;
        }
        
        .in-stock { background: #d4edda; color: #155724; }
        .low-stock { background: #fff3cd; color: #856404; }
        .out-stock { background: #f8d7da; color: #721c24; }
        
        .price-column {
            font-weight: bold;
            color: #27ae60;
            font-size: 1.1em;
        }
        
        .quick-reference {
            margin-top: 30px;
            background: linear-gradient(45deg, #f8f9fa, #e9ecef);
            padding: 25px;
            border-radius: 15px;
            border-left: 6px solid #27ae60;
        }
        
        .reference-title {
            color: #27ae60;
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .appliance-section {
            margin-bottom: 25px;
        }
        
        .appliance-section h4 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 1.2em;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .issue-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }
        
        .issue-btn {
            padding: 10px 18px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 0.95em;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        
        .issue-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.2);
        }
        
        .issue-btn.washer { background: #e3f2fd; color: #1976d2; }
        .issue-btn.dryer { background: #fff3e0; color: #f57c00; }
        .issue-btn.dishwasher { background: #fce4ec; color: #c2185b; }
        .issue-btn.refrigerator { background: #e8f5e8; color: #388e3c; }
        .issue-btn.range { background: #fff8e1; color: #f9a825; }
        
        .no-results {
            text-align: center;
            padding: 50px;
            color: #7f8c8d;
            font-style: italic;
            font-size: 1.2em;
        }
        
        .help-text {
            background: #e8f6fd;
            padding: 15px 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            border-left: 4px solid #3498db;
            color: #2c3e50;
        }
        
        @media (max-width: 768px) {
            .container { margin: 10px; padding: 15px; }
            .header h1 { font-size: 2.2em; }
            .stats { gap: 20px; }
            .stat-item { padding: 15px 25px; }
            .filters { flex-direction: column; }
            .customer-questions { grid-template-columns: 1fr; }
            table { font-size: 0.9em; }
            th, td { padding: 10px; }
            .quick-tools { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🔧 Counter Sales Knowledge Base</h1>
            <div class="subtitle">Stevens Parts - Professional Customer Service System</div>
            <div class="stats">
                <div class="stat-item">
                    <span class="stat-number" id="totalParts">312</span>
                    <span>Control Boards</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">4</span>
                    <span>Major Brands</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">5</span>
                    <span>Appliance Types</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">24/7</span>
                    <span>Support</span>
                </div>
            </div>
        </div>

        <div class="quick-tools">
            <div class="tool-card">
                <h3>📞 Customer Call Protocol</h3>
                <div class="help-text">
                    <strong>Step 1:</strong> Get appliance brand and type<br>
                    <strong>Step 2:</strong> Ask about specific symptoms<br>
                    <strong>Step 3:</strong> Search for matching control boards<br>
                    <strong>Step 4:</strong> Check stock and provide pricing
                </div>
            </div>
            
            <div class="tool-card">
                <h3>🔍 Quick Search Tips</h3>
                <div class="help-text">
                    <strong>Part Numbers:</strong> Enter full or partial numbers<br>
                    <strong>Symptoms:</strong> Search "won't drain" or "no heat"<br>
                    <strong>Models:</strong> Enter customer's model number<br>
                    <strong>Error Codes:</strong> Search F21, OE, 4C, etc.
                </div>
            </div>
            
            <div class="tool-card">
                <h3>📊 Stock Status Guide</h3>
                <div class="help-text">
                    <strong style="color: #27ae60;">In Stock:</strong> Ships same day<br>
                    <strong style="color: #f39c12;">Low Stock:</strong> 1-2 day lead time<br>
                    <strong style="color: #e74c3c;">Out of Stock:</strong> 3-7 day back-order
                </div>
            </div>
        </div>

        <div class="filters">
            <div class="filter-group">
                <label for="brandFilter">🏷️ Brand:</label>
                <select id="brandFilter" onchange="filterTable()">
                    <option value="">All Brands</option>
                    <option value="Whirlpool">Whirlpool</option>
                    <option value="GE">GE</option>
                    <option value="LG">LG</option>
                    <option value="Samsung">Samsung</option>
                </select>
            </div>
            
            <div class="filter-group">
                <label for="applianceFilter">🏠 Appliance:</label>
                <select id="applianceFilter" onchange="filterTable()">
                    <option value="">All Appliances</option>
                    <option value="Washer">Washers</option>
                    <option value="Dryer">Dryers</option>
                    <option value="Dishwasher">Dishwashers</option>
                    <option value="Refrigerator">Refrigerators</option>
                    <option value="Range">Ranges/Ovens</option>
                </select>
            </div>
            
            <div class="filter-group">
                <label for="stockFilter">📦 Stock:</label>
                <select id="stockFilter" onchange="filterTable()">
                    <option value="">All Stock Levels</option>
                    <option value="In Stock">In Stock Only</option>
                    <option value="Low Stock">Low Stock</option>
                    <option value="Out of Stock">Back Order</option>
                </select>
            </div>
            
            <div class="filter-group">
                <label for="priceFilter">💰 Price Range:</label>
                <select id="priceFilter" onchange="filterTable()">
                    <option value="">All Prices</option>
                    <option value="0-100">Under $100</option>
                    <option value="100-200">$100 - $200</option>
                    <option value="200-300">$200 - $300</option>
                    <option value="300+">Over $300</option>
                </select>
            </div>
            
            <div class="filter-group search-box">
                <label for="searchInput">🔍 Search:</label>
                <input type="text" id="searchInput" placeholder="Part#, model, error code, or symptom..." oninput="filterTable()">
            </div>
        </div>

        <div class="diagnostic-section" id="diagnosticSection">
            <div class="diagnostic-title" id="diagnosticTitle">
                🩺 <span id="brandName">Whirlpool</span> Customer Questions
            </div>
            <div class="customer-questions" id="customerQuestions">
                <!-- Will be populated by JavaScript -->
            </div>
        </div>

        <div class="table-container">
            <div class="table-header">
                <span>🗄️ Parts Inventory Database</span>
                <span><span id="filteredCount">312</span> items shown</span>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Part Number</th>
                        <th>Brand</th>
                        <th>Appliance</th>
                        <th>Description</th>
                        <th>Common Issues</th>
                        <th>Compatible Models</th>
                        <th>Price</th>
                        <th>Stock Status</th>
                    </tr>
                </thead>
                <tbody id="inventoryTable">
                    <!-- Will be populated by JavaScript -->
                </tbody>
            </table>
            <div id="noResults" class="no-results" style="display: none;">
                🤷‍♂️ No parts match your search criteria.<br>
                Try adjusting your filters or search terms.
            </div>
        </div>

        <div class="quick-reference">
            <div class="reference-title">
                ⚡ Common Issues Quick Reference
            </div>
            
            <div class="appliance-section">
                <h4>🧺 Washer Issues (Click to Search):</h4>
                <div class="issue-buttons">
                    <button class="issue-btn washer" onclick="searchIssue('drain pump')">Won't Drain</button>
                    <button class="issue-btn washer" onclick="searchIssue('water valve')">Won't Fill</button>
                    <button class="issue-btn washer" onclick="searchIssue('lid lock')">Door/Lid Lock</button>
                    <button class="issue-btn washer" onclick="searchIssue('motor control')">Won't Spin</button>
                    <button class="issue-btn washer" onclick="searchIssue('F21')">Error F21</button>
                    <button class="issue-btn washer" onclick="searchIssue('display')">Display Dead</button>
                </div>
            </div>
            
            <div class="appliance-section">
                <h4>🌪️ Dryer Issues (Click to Search):</h4>
                <div class="issue-buttons">
                    <button class="issue-btn dryer" onclick="searchIssue('heating element')">No Heat</button>
                    <button class="issue-btn dryer" onclick="searchIssue('temperature')">Wrong Temperature</button>
                    <button class="issue-btn dryer" onclick="searchIssue('moisture sensor')">Won't Stop</button>
                    <button class="issue-btn dryer" onclick="searchIssue('timer')">Timer Issues</button>
                    <button class="issue-btn dryer" onclick="searchIssue('gas valve')">Gas Not Igniting</button>
                </div>
            </div>
            
            <div class="appliance-section">
                <h4>🍽️ Dishwasher Issues (Click to Search):</h4>
                <div class="issue-buttons">
                    <button class="issue-btn dishwasher" onclick="searchIssue('wash pump')">Won't Wash</button>
                    <button class="issue-btn dishwasher" onclick="searchIssue('drain pump')">Won't Drain</button>
                    <button class="issue-btn dishwasher" onclick="searchIssue('dispenser')">Soap Dispenser</button>
                    <button class="issue-btn dishwasher" onclick="searchIssue('heating element')">Dishes Don't Dry</button>
                    <button class="issue-btn dishwasher" onclick="searchIssue('door latch')">Door Problems</button>
                </div>
            </div>
            
            <div class="appliance-section">
                <h4>❄️ Refrigerator Issues (Click to Search):</h4>
                <div class="issue-buttons">
                    <button class="issue-btn refrigerator" onclick="searchIssue('ice maker')">Ice Maker</button>
                    <button class="issue-btn refrigerator" onclick="searchIssue('temperature control')">Temperature</button>
                    <button class="issue-btn refrigerator" onclick="searchIssue('defrost')">Defrost Problems</button>
                    <button class="issue-btn refrigerator" onclick="searchIssue('compressor')">Not Cooling</button>
                    <button class="issue-btn refrigerator" onclick="searchIssue('water filter')">Water/Ice Taste</button>
                </div>
            </div>
            
            <div class="appliance-section">
                <h4>🔥 Range/Oven Issues (Click to Search):</h4>
                <div class="issue-buttons">
                    <button class="issue-btn range" onclick="searchIssue('bake element')">Oven No Heat</button>
                    <button class="issue-btn range" onclick="searchIssue('igniter')">Gas Won't Light</button>
                    <button class="issue-btn range" onclick="searchIssue('temperature sensor')">Wrong Temperature</button>
                    <button class="issue-btn range" onclick="searchIssue('control board')">Display Issues</button>
                    <button class="issue-btn range" onclick="searchIssue('door lock')">Self-Clean Lock</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Brand-specific customer service questions
        const brandQuestions = {
            'Whirlpool': [
                { key: 'error_codes', title: '🚨 What error code is displayed?', desc: 'F21 (drain), F28 (communication), F35 (pressure), F51 (motor), etc.' },
                { key: 'symptoms', title: '🔍 What exactly is it doing?', desc: 'Won\'t start, stops mid-cycle, loud noises, leaking, no heat' },
                { key: 'model_info', title: '📋 What\'s the complete model number?', desc: 'Usually on inside door rim or back panel (WFW, WED, WDT, WRS, etc.)' },
                { key: 'age_warranty', title: '📅 How old is the appliance?', desc: 'Under 1 year may be warranty, over 10 years consider replacement' },
                { key: 'power_display', title: '💡 Does it have power/lights?', desc: 'Completely dead vs partial function helps narrow diagnosis' },
                { key: 'recent_changes', title: '🔧 Any recent repairs or moves?', desc: 'Installation issues, previous repairs, power outages, etc.' }
            ],
            'GE': [
                { key: 'error_codes', title: '🚨 Any error codes showing?', desc: 'E10, E20, E23 (water issues), E30 (door), E40 (motor), etc.' },
                { key: 'smart_features', title: '📱 Is this a smart/WiFi model?', desc: 'SmartHQ app issues, connectivity problems, smart dispense' },
                { key: 'specific_symptoms', title: '🔍 Describe the exact problem', desc: 'When does it happen? During what cycle? Consistent or intermittent?' },
                { key: 'model_series', title: '📋 What series is it?', desc: 'Profile, Café, Artistry, or standard GE? Check model plate' },
                { key: 'installation_check', title: '🏠 Installation environment?', desc: 'Level? Proper power? Water pressure? Drainage setup?' },
                { key: 'maintenance_history', title: '🧽 When was it last serviced?', desc: 'Cleaning, filter changes, maintenance cycle usage' }
            ],
            'LG': [
                { key: 'error_codes', title: '🚨 What error code appears?', desc: 'OE (drain), UE (unbalanced), LE (motor), FE (water overflow), etc.' },
                { key: 'thinq_issues', title: '📱 ThinQ app problems?', desc: 'WiFi connectivity, smart diagnosis, remote control features' },
                { key: 'direct_drive', title: '🔄 Direct Drive motor issues?', desc: 'Unusual noises, vibration, grinding sounds during wash/spin' },
                { key: 'steam_features', title: '💨 Steam function problems?', desc: 'Steam wash, allergiene, steam fresh, or steam clean not working' },
                { key: 'load_sensing', title: '⚖️ Load sensing acting up?', desc: 'Adding too much/little water, cycle times way too long/short' },
                { key: 'model_features', title: '📋 Which LG features does it have?', desc: 'TurboWash, SideKick pedestal, TWINWash, 6Motion technology' }
            ],
            'Samsung': [
                { key: 'error_codes', title: '🚨 Error codes displayed?', desc: '4C/5C (water), DC (door), UC (unbalanced), 1C (sensor), etc.' },
                { key: 'smartthings', title: '📱 SmartThings connectivity?', desc: 'App control, notifications, smart diagnosis, remote monitoring' },
                { key: 'addwash_features', title: '🚪 AddWash door problems?', desc: 'Secondary door won\'t open/close, mid-cycle adding issues' },
                { key: 'ecobubble', title: '🫧 EcoBubble function issues?', desc: 'Bubble generator, detergent mixing, cleaning performance' },
                { key: 'digital_inverter', title: '⚡ Digital Inverter problems?', desc: 'Motor noise, speed control, energy efficiency concerns' },
                { key: 'self_maintenance', title: '🧼 Self Clean alerts?', desc: 'Self Clean+ cycle, maintenance reminders, drum cleaning' }
            ]
        };

        // Comprehensive parts database
        const partsDatabase = [
            // Whirlpool Washers (Front Load)
            { partNumber: 'W10310240', brand: 'Whirlpool', appliance: 'Washer', description: 'Main Electronic Control Board - Duet', commonIssues: 'No power, display dead, F21/F28 errors', models: 'WFW9150WW, WFW8500DC, WFW9250WL', price: 189.95, stock: 'In Stock' },
            { partNumber: 'W10393156', brand: 'Whirlpool', appliance: 'Washer', description: 'Door Lock Control Board', commonIssues: 'Door won\'t lock/unlock, F35 error, lid lock failure', models: 'WFW8400TW, WFW8500SR, WFW9050XW', price: 156.75, stock: 'In Stock' },
            { partNumber: 'W11027055', brand: 'Whirlpool', appliance: 'Washer', description: 'Smart WiFi Control Board', commonIssues: 'WiFi connectivity lost, app won\'t connect, smart features down', models: 'WFW6620HC, WFW8620HC, WFW9620HC', price: 234.50, stock: 'Low Stock' },
            { partNumber: 'W11032443', brand: 'Whirlpool', appliance: 'Washer', description: 'Load & Go Dispenser Control', commonIssues: 'Auto-dispense not working, detergent sensing errors', models: 'WFW5620HW, WFW8620HW, WFW9620HW', price: 198.25, stock: 'In Stock' },
            
            // Whirlpool Washers (Top Load)
            { partNumber: 'W10084142', brand: 'Whirlpool', appliance: 'Washer', description: 'Top Load HE Control Board', commonIssues: 'Lid lock issues, water level sensing, F51 motor error', models: 'WTW8500DC, WTW8700EC, WTW8800YC', price: 167.89, stock: 'In Stock' },
            { partNumber: 'W10911679', brand: 'Whirlpool', appliance: 'Washer', description: 'Smart Cabrio Control Board', commonIssues: 'Load sensing problems, cycle selection issues', models: 'WTW5000DW, WTW7000DW, WTW8000DW', price: 201.50, stock: 'In Stock' },
            { partNumber: 'W11035949', brand: 'Whirlpool', appliance: 'Washer', description: 'Color Touch Display Control', commonIssues: 'Screen not responding, display flickering, touch sensitivity', models: 'WTW8127LC, WTW8500DC, WTW8700EC', price: 276.95, stock: 'Low Stock' },
            
            // Whirlpool Dryers
            { partNumber: 'W10111606', brand: 'Whirlpool', appliance: 'Dryer', description: 'Electric Dryer Control Board', commonIssues: 'No heat, timer stuck, cycle won\'t advance', models: 'WED9150WW, WED8500DC, WED9250WL', price: 145.75, stock: 'In Stock' },
            { partNumber: 'W10476828', brand: 'Whirlpool', appliance: 'Dryer', description: 'Gas Dryer Control Board', commonIssues: 'Gas valve not opening, ignition problems, temperature issues', models: 'WGD9150WW, WGD8500DC, WGD9250WL', price: 178.95, stock: 'In Stock' },
            { partNumber: 'W11035891', brand: 'Whirlpool', appliance: 'Dryer', description: 'Steam Dryer Control Board', commonIssues: 'Steam function not working, moisture sensing problems', models: 'WED8620HC, WGD8620HC, WED9620HC', price: 223.50, stock: 'Low Stock' },
            
            // Whirlpool Dishwashers
            { partNumber: 'W11088843', brand: 'Whirlpool', appliance: 'Dishwasher', description: 'Dishwasher Electronic Control', commonIssues: 'Won\'t start cycle, display blank, button not responding', models: 'WDT750SAHZ, WDT730PAHZ, WDF520PADM', price: 189.25, stock: 'In Stock' },
            { partNumber: 'W10906394', brand: 'Whirlpool', appliance: 'Dishwasher', description: 'Smart Dishwasher Control Board', commonIssues: 'WiFi issues, smart features not working, app connectivity', models: 'WDT975SAHZ, WDT970SAHZ, WDTA50SAHZ', price: 256.75, stock: 'In Stock' },
            
            // Whirlpool Refrigerators
            { partNumber: 'W10310240', brand: 'Whirlpool', appliance: 'Refrigerator', description: 'French Door Refrigerator Control', commonIssues: 'Temperature control issues, ice maker problems, defrost failure', models: 'WRF535SWHZ, WRF757SDHZ, WRF767SDHZ', price: 298.95, stock: 'In Stock' },
            { partNumber: 'W11035747', brand: 'Whirlpool', appliance: 'Refrigerator', description: 'Smart Refrigerator Control Board', commonIssues: 'WiFi connectivity, smart features, temperature monitoring', models: 'WRS588FIHZ, WRS571CIHZ, WRF540CWHZ', price: 334.50, stock: 'Low Stock' },

            // GE Washers
            { partNumber: 'WH12X10355', brand: 'GE', appliance: 'Washer', description: 'Front Load Washer Control Board', commonIssues: 'E20 error, door lock failure, drain pump control', models: 'GFW850SPNDG, GFW650SSNWW, GFW148SSLWW', price: 198.75, stock: 'In Stock' },
            { partNumber: 'WH12X10439', brand: 'GE', appliance: 'Washer', description: 'SmartDispense Control Board', commonIssues: 'Auto-dispense failure, detergent sensing, E23 water errors', models: 'GFW850SPNDG, GFW650SSNWW, GFW450SSMWW', price: 267.50, stock: 'In Stock' },
            { partNumber: 'WH12X10540', brand: 'GE', appliance: 'Washer', description: 'UltraFresh Vent Control Board', commonIssues: 'Odor control not working, ventilation fan issues', models: 'GFW850SPNRS, GFW650SSNRG, GFW450SSMRG', price: 289.95, stock: 'Low Stock' },
            { partNumber: 'WH12X10612', brand: 'GE', appliance: 'Washer', description: 'Top Load Smart Control Board', commonIssues: 'Load sensing problems, WiFi connectivity, smart features', models: 'GTW755CSLWS, GTW335ASNWW, GTW485ASJWS', price: 234.25, stock: 'In Stock' },
            
            // GE Dryers
            { partNumber: 'WE4M533', brand: 'GE', appliance: 'Dryer', description: 'Dryer Electronic Control Board', commonIssues: 'No heat, cycle problems, timer issues, E40 errors', models: 'GFD85ESSNWW, GFD65ESSNWW, GFD45ESSMWW', price: 167.89, stock: 'In Stock' },
            { partNumber: 'WE4M564', brand: 'GE', appliance: 'Dryer', description: 'Smart Dryer Control Board', commonIssues: 'WiFi connectivity issues, SmartHQ app problems', models: 'GFD85ESPNRS, GFD65ESPNRG, GFD45ESPMRG', price: 245.75, stock: 'In Stock' },
            { partNumber: 'WE4M601', brand: 'GE', appliance: 'Dryer', description: 'Steam Dryer Control Board', commonIssues: 'Steam cycles not working, sanitize function failure', models: 'GFD85ESSNWW, GFD65ESSNWW, GTD85ESSNWS', price: 278.50, stock: 'Low Stock' },
            
            // GE Dishwashers
            { partNumber: 'WD21X23734', brand: 'GE', appliance: 'Dishwasher', description: 'Dishwasher Control Board', commonIssues: 'Won\'t start, cycle interruption, display problems', models: 'GDT695SSJSS, GDT545PSJSS, GDP615HSNSS', price: 178.95, stock: 'In Stock' },
            { partNumber: 'WD21X24901', brand: 'GE', appliance: 'Dishwasher', description: 'WiFi Connect Dishwasher Control', commonIssues: 'SmartHQ connectivity, WiFi setup, remote control', models: 'CDT875P2NS1, GDT695SGJBB, PDT775SSNSS', price: 234.75, stock: 'In Stock' },
            
            // GE Refrigerators
            { partNumber: 'WR55X23169', brand: 'GE', appliance: 'Refrigerator', description: 'French Door Refrigerator Control', commonIssues: 'Temperature fluctuation, ice maker control, defrost issues', models: 'GFE28GYNFS, GFE26JYNFS, GNE27JYNFS', price: 289.50, stock: 'In Stock' },
            { partNumber: 'WR55X26212', brand: 'GE', appliance: 'Refrigerator', description: 'SmartHQ WiFi Control Board', commonIssues: 'WiFi connectivity, app control, smart alerts', models: 'GFE28GYNFS, GYE22GYNFS, PYE22GYNFS', price: 345.75, stock: 'Low Stock' },

            // GE Ranges
            { partNumber: 'WB27K10355', brand: 'GE', appliance: 'Range', description: 'Oven Control Board', commonIssues: 'Oven won\'t heat, temperature inaccurate, display issues', models: 'JB735SPSS, JB645RKSS, JGS750SPSS', price: 234.95, stock: 'In Stock' },
            { partNumber: 'WB27K10419', brand: 'GE', appliance: 'Range', description: 'Self-Clean Oven Control', commonIssues: 'Self-clean cycle failure, door lock problems', models: 'JB735SPSS, JGS750SPSS, JGB735SPSS', price: 267.50, stock: 'In Stock' },

            // LG Washers
            { partNumber: 'EBR78534409', brand: 'LG', appliance: 'Washer', description: 'Direct Drive Main Control Board', commonIssues: 'OE/UE errors, motor control, inverter problems', models: 'WM3900HWA, WM4000HWA, WM3700HWA', price: 208.75, stock: 'In Stock' },
            { partNumber: 'EBR85234512', brand: 'LG', appliance: 'Washer', description: 'ThinQ Smart Control Board', commonIssues: 'WiFi connectivity, ThinQ app issues, smart diagnosis', models: 'WM9000HVA, WM8100HVA, WM5000HWA', price: 298.50, stock: 'In Stock' },
            { partNumber: 'EBR89234667', brand: 'LG', appliance: 'Washer', description: 'Steam Wash Control Board', commonIssues: 'Steam wash not working, allergiene cycle failure', models: 'WM4370HKA, WM3770HWA, WM3570HWA', price: 256.95, stock: 'Low Stock' },
            { partNumber: 'EBR91234788', brand: 'LG', appliance: 'Washer', description: 'TurboWash Control Board', commonIssues: 'TurboWash jets not working, spray arm failure', models: 'WM5000HWA, WM4500HBA, WM3900HBA', price: 278.75, stock: 'In Stock' },
            
            // LG Dryers  
            { partNumber: 'EBR78945123', brand: 'LG', appliance: 'Dryer', description: 'Inverter Dryer Control Board', commonIssues: 'Motor speed control, energy efficiency, LE error codes', models: 'DLG7201WE, DLE7200WE, DLEX3900W', price: 198.95, stock: 'In Stock' },
            { partNumber: 'EBR85467234', brand: 'LG', appliance: 'Dryer', description: 'ThinQ Smart Dryer Control', commonIssues: 'WiFi issues, app connectivity, smart diagnosis', models: 'DLEX9000V, DLGX9001V, DLEX7600WE', price: 267.50, stock: 'In Stock' },
            { partNumber: 'EBR87234591', brand: 'LG', appliance: 'Dryer', description: 'Steam Dryer Control Board', commonIssues: 'Steam refresh not working, sanitize cycle problems', models: 'DLEX4270W, DLGX4271W, DLEX3570W', price: 289.75, stock: 'Low Stock' },
            
            // LG Dishwashers
            { partNumber: 'EBR83412678', brand: 'LG', appliance: 'Dishwasher', description: 'QuadWash Control Board', commonIssues: 'Spray arm control, wash cycle issues, OE drain error', models: 'LDF5545ST, LDP6797ST, LDT7797ST', price: 234.50, stock: 'In Stock' },
            { partNumber: 'EBR88745123', brand: 'LG', appliance: 'Dishwasher', description: 'ThinQ Smart Dishwasher Control', commonIssues: 'WiFi connectivity, smart features, app remote control', models: 'LDT9965BD, LDP6809SS, LDFN4542S', price: 278.95, stock: 'In Stock' },
            
            // LG Refrigerators
            { partNumber: 'EBR79234588', brand: 'LG', appliance: 'Refrigerator', description: 'InstaView Control Board', commonIssues: 'Door display not working, knock sensor failure', models: 'LMXS28596S, LMXC23796S, LRFXC2406S', price: 345.75, stock: 'In Stock' },
            { partNumber: 'EBR84567234', brand:'LG', appliance: 'Refrigerator', description: 'Smart ThinQ Refrigerator Control', commonIssues: 'WiFi connectivity, smart diagnosis, temperature control', models: 'LRFVS3006S, LRFXS2503S, LRMVS3006S', price: 398.50, stock: 'Low Stock' },

            // LG Ranges
            { partNumber: 'EBR87654321', brand: 'LG', appliance: 'Range', description: 'Smart Oven Control Board', commonIssues: 'Oven temperature issues, WiFi connectivity, smart features', models: 'LREL6323S, LRGL5825F, LTGL6937F', price: 298.75, stock: 'In Stock' },

            // Samsung Washers
            { partNumber: 'DC92-01021A', brand: 'Samsung', appliance: 'Washer', description: 'Front Load Washer Control Board', commonIssues: '4C/5C water errors, DC door error, cycle problems', models: 'WF45R6100AW, WF50R8500AV, WF45R6300AW', price: 212.95, stock: 'In Stock' },
            { partNumber: 'DC92-02057A', brand: 'Samsung', appliance: 'Washer', description: 'SmartThings WiFi Control Board', commonIssues: 'SmartThings connectivity, app control, remote monitoring', models: 'WF50R8500AV, WF45R6300AW, WF50K7500AV', price: 289.50, stock: 'In Stock' },
            { partNumber: 'DC92-02134B', brand: 'Samsung', appliance: 'Washer', description: 'AddWash Control Board', commonIssues: 'AddWash door not opening, mid-cycle door sensor', models: 'WF50R8500AV, WF45R6300AW, WF50K7500AW', price: 256.75, stock: 'Low Stock' },
            { partNumber: 'DC92-02189C', brand: 'Samsung', appliance: 'Washer', description: 'EcoBubble Control Board', commonIssues: 'Bubble generation failure, detergent mixing issues', models: 'WF45T6000AW, WF50R8500AV, WF45R6100AW', price: 234.95, stock: 'In Stock' },
            
            // Samsung Dryers
            { partNumber: 'DC92-01623A', brand: 'Samsung', appliance: 'Dryer', description: 'Digital Inverter Dryer Control', commonIssues: 'Motor control issues, energy efficiency problems, noise', models: 'DV50R8500V, DV45R6300EW, DV50R5400W', price: 198.75, stock: 'In Stock' },
            { partNumber: 'DC92-02045B', brand: 'Samsung', appliance: 'Dryer', description: 'SmartThings Dryer Control', commonIssues: 'WiFi connectivity, app control, smart notifications', models: 'DV50R8500V, DV45R6300EW, DV50K7500EV', price: 267.50, stock: 'In Stock' },
            { partNumber: 'DC92-02156C', brand: 'Samsung', appliance: 'Dryer', description: 'Steam Sanitize Control Board', commonIssues: 'Steam functions not working, sanitize cycle failure', models: 'DV50R8500V, DV45R6300EW, DV45T6000EW', price: 289.95, stock: 'Low Stock' },
            
            // Samsung Dishwashers
            { partNumber: 'DD82-01234A', brand: 'Samsung', appliance: 'Dishwasher', description: 'WaterWall Dishwasher Control', commonIssues: 'WaterWall technology failure, spray issues, cycle problems', models: 'DW80R9950US, DW80R7060US, DW80R5060US', price: 298.50, stock: 'In Stock' },
            { partNumber: 'DD82-02145B', brand: 'Samsung', appliance: 'Dishwasher', description: 'SmartThings Dishwasher Control', commonIssues: 'WiFi connectivity, app control, smart features', models: 'DW80R9950US, DW80R7060US, DW80T7550US', price: 334.75, stock: 'In Stock' },
            
            // Samsung Refrigerators  
            { partNumber: 'DA41-00814A', brand: 'Samsung', appliance: 'Refrigerator', description: 'Family Hub Control Board', commonIssues: 'Touchscreen not responding, WiFi issues, app connectivity', models: 'RF28R7351SG, RF23M8070SR, RF28R7551SR', price: 456.95, stock: 'In Stock' },
            { partNumber: 'DA41-00923B', brand: 'Samsung', appliance: 'Refrigerator', description: 'FlexZone Control Board', commonIssues: 'FlexZone temperature control, convertible drawer issues', models: 'RF28R7351SG, RF23M8090SG, RF28R7201SR', price: 378.50, stock: 'Low Stock' },

            // Samsung Ranges
            { partNumber: 'DE92-03045A', brand: 'Samsung', appliance: 'Range', description: 'Smart Oven Control Board', commonIssues: 'Oven temperature control, WiFi connectivity, smart features', models: 'NE63T8751SS, NX60T8511SS, NY63T8751SS', price: 312.75, stock: 'In Stock' }
        ];

        let filteredData = [...partsDatabase];
        let currentBrand = 'Whirlpool';

        function updateCustomerQuestions(brand) {
            currentBrand = brand || 'Whirlpool';
            const brandNameElement = document.getElementById('brandName');
            const questionsElement = document.getElementById('customerQuestions');
            
            brandNameElement.textContent = currentBrand;
            
            const questions = brandQuestions[currentBrand] || brandQuestions['Whirlpool'];
            questionsElement.innerHTML = questions.map(q => `
                <div class="customer-question" onclick="searchIssue('${q.key}')">
                    <div class="question-title">${q.title}</div>
                    <div class="question-desc">${q.desc}</div>
                </div>
            `).join('');
        }

        function filterTable() {
            const brandFilter = document.getElementById('brandFilter').value;
            const applianceFilter = document.getElementById('applianceFilter').value;
            const stockFilter = document.getElementById('stockFilter').value;
            const priceFilter = document.getElementById('priceFilter').value;
            const searchInput = document.getElementById('searchInput').value.toLowerCase();

            // Update customer questions when brand changes
            if (brandFilter && brandFilter !== currentBrand) {
                updateCustomerQuestions(brandFilter);
            } else if (!brandFilter) {
                updateCustomerQuestions('Whirlpool');
            }

            filteredData = partsDatabase.filter(item => {
                const matchesBrand = !brandFilter || item.brand === brandFilter;
                const matchesAppliance = !applianceFilter || item.appliance === applianceFilter;
                const matchesStock = !stockFilter || item.stock === stockFilter;
                
                let matchesPrice = true;
                if (priceFilter) {
                    const price = item.price;
                    switch(priceFilter) {
                        case '0-100': matchesPrice = price < 100; break;
                        case '100-200': matchesPrice = price >= 100 && price < 200; break;
                        case '200-300': matchesPrice = price >= 200 && price < 300; break;
                        case '300+': matchesPrice = price >= 300; break;
                    }
                }
                
                const matchesSearch = !searchInput || 
                    item.partNumber.toLowerCase().includes(searchInput) ||
                    item.description.toLowerCase().includes(searchInput) ||
                    item.commonIssues.toLowerCase().includes(searchInput) ||
                    item.models.toLowerCase().includes(searchInput) ||
                    item.brand.toLowerCase().includes(searchInput);

                return matchesBrand && matchesAppliance && matchesStock && matchesPrice && matchesSearch;
            });

            displayResults();
        }

        function displayResults() {
            const tbody = document.getElementById('inventoryTable');
            const noResults = document.getElementById('noResults');
            const filteredCount = document.getElementById('filteredCount');

            if (filteredData.length === 0) {
                tbody.innerHTML = '';
                noResults.style.display = 'block';
                filteredCount.textContent = '0';
                return;
            }

            noResults.style.display = 'none';
            filteredCount.textContent = filteredData.length;

            tbody.innerHTML = filteredData.map(item => `
                <tr>
                    <td class="part-number">${item.partNumber}</td>
                    <td><span class="brand-badge brand-${item.brand.toLowerCase()}">${item.brand}</span></td>
                    <td>${item.appliance}</td>
                    <td>${item.description}</td>
                    <td>${item.commonIssues}</td>
                    <td>${item.models}</td>
                    <td class="price-column">$${item.price.toFixed(2)}</td>
                    <td><span class="stock-indicator ${item.stock.replace(' ', '-').toLowerCase()}">${item.stock}</span></td>
                </tr>
            `).join('');
        }

        function searchIssue(issue) {
            document.getElementById('searchInput').value = issue;
            filterTable();
            
            // Scroll to results
            document.querySelector('.table-container').scrollIntoView({ 
                behavior: 'smooth',
                block: 'start'
            });

            // Highlight the search briefly
            setTimeout(() => {
                const searchInput = document.getElementById('searchInput');
                searchInput.style.background = '#3498db';
                searchInput.style.color = 'white';
                setTimeout(() => {
                    searchInput.style.background = '';
                    searchInput.style.color = '';
                }, 1500);
            }, 500);
        }

        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            updateCustomerQuestions('Whirlpool');
            displayResults();
        });
    </script>
</body>
</html>

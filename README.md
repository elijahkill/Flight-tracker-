<!DOCTYPE html>
<html>
<head>
    <title>Flight Ticket Tracker</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: #f0f8ff;
            margin: 0;
            padding: 20px;
            color: #333;
        }
        .ticket {
            background: white;
            max-width: 500px;
            margin: 20px auto;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            border-left: 5px solid #0066cc;
        }
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        .airline {
            font-size: 24px;
            font-weight: bold;
            color: #0066cc;
        }
        .flight-number {
            background: #0066cc;
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            font-weight: bold;
        }
        .route {
            display: flex;
            justify-content: space-between;
            margin: 30px 0;
        }
        .airport {
            text-align: center;
        }
        .city {
            font-size: 24px;
            font-weight: bold;
        }
        .code {
            color: #666;
        }
        .time {
            font-size: 20px;
            font-weight: bold;
        }
        .date {
            color: #666;
        }
        .status {
            background: #f0f0f0;
            padding: 10px;
            border-radius: 5px;
            margin: 20px 0;
            text-align: center;
            font-weight: bold;
        }
        .on-time {
            color: #2e8b57;
        }
        .delayed {
            color: #e63946;
        }
        .details {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px dashed #ccc;
        }
        .detail-item {
            text-align: center;
        }
        .detail-label {
            color: #666;
            font-size: 14px;
        }
        .detail-value {
            font-weight: bold;
            margin-top: 5px;
        }
        .refresh-btn {
            display: block;
            width: 100%;
            padding: 10px;
            background: #0066cc;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
        }
        .refresh-btn:hover {
            background: #004d99;
        }
    </style>
</head>
<body>
    <div class="ticket">
        <div class="header">
            <div class="airline">SKY WINGS AIR</div>
            <div class="flight-number">SWA 247</div>
        </div>
        
        <div class="route">
            <div class="airport">
                <div class="city">Lagos</div>
                <div class="code">LOS</div>
                <div class="time">14:30</div>
                <div class="date">15 Oct 2024</div>
            </div>
            <div class="airport">
                <div style="font-size: 24px;">→</div>
            </div>
            <div class="airport">
                <div class="city">London</div>
                <div class="code">LHR</div>
                <div class="time">21:00</div>
                <div class="date">15 Oct 2024</div>
            </div>
        </div>
        
        <div class="status on-time">
            ● Flight Status: ON TIME
        </div>
        
        <div class="details">
            <div class="detail-item">
                <div class="detail-label">Passenger</div>
                <div class="detail-value">John Doe</div>
            </div>
            <div class="detail-item">
                <div class="detail-label">Seat</div>
                <div class="detail-value">24A</div>
            </div>
            <div class="detail-item">
                <div class="detail-label">Gate</div>
                <div class="detail-value">B12</div>
            </div>
            <div class="detail-item">
                <div class="detail-label">Boarding</div>
                <div class="detail-value">13:45</div>
            </div>
        </div>
        
        <button class="refresh-btn" onclick="refreshFlight()">Refresh Status</button>
    </div>

    <script>
        function refreshFlight() {
            const status = document.querySelector('.status');
            const randomStatus = Math.random() > 0.2 ? 'ON TIME' : 'DELAYED';
            
            if (randomStatus === 'DELAYED') {
                status.textContent = '● Flight Status: DELAYED (New dep: 15:45)';
                status.className = 'status delayed';
            } else {
                status.textContent = '● Flight Status: ON TIME';
                status.className = 'status on-time';
            }
            
            alert('Flight status updated!');
        }
    </script>
</body>
</html>

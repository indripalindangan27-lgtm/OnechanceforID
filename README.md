<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personal Growth Dashboard</title>
    <style>
        :root {
            --primary-green: #A8DADC;
            --white: #FFFFFF;
            --beige: #F7F3E9;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            --border-radius: 8px;
            --transition: all 0.3s ease;
        }
        body {
            font-family: 'Nunito', sans-serif; /* Rounded sans-serif */
            background: linear-gradient(135deg, var(--beige), var(--white));
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            color: var(--primary-green);
        }
        h1 {
            font-size: 2rem;
            margin-bottom: 40px;
            position: relative;
        }
        h1::after {
            content: '';
            position: absolute;
            top: 10px;
            right: -30px;
            width: 20px;
            height: 20px;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23A8DADC' stroke-width='1' opacity='0.3'%3E%3Cpath d='M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z'/%3E%3C/svg%3E") no-repeat;
        }
        .dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            max-width: 1000px;
            width: 100%;
        }
        .card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px); /* Glassmorphism */
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 20px;
            text-align: center;
            position: relative;
            transition: var(--transition);
            overflow: hidden;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }
        .card::before {
            content: '';
            position: absolute;
            top: 10px;
            right: 10px;
            width: 15px;
            height: 15px;
            background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23A8DADC' stroke-width='1' opacity='0.3'%3E%3Cpath d='M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z'/%3E%3C/svg%3E") no-repeat;
            opacity: 0.3;
        }
        .progress-ring {
            width: 120px;
            height: 120px;
            margin: 0 auto 20px;
        }
        .progress-ring circle {
            fill: none;
            stroke: var(--beige);
            stroke-width: 8;
        }
        .progress-ring .progress {
            stroke: var(--primary-green);
            stroke-linecap: round;
            transition: stroke-dasharray 0.5s ease-in-out;
        }
        .percentage {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 20px;
        }
        .controls {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        button {
            background: var(--primary-green);
            color: var(--white);
            border: none;
            border-radius: var(--border-radius);
            padding: 8px 12px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1.2rem;
        }
        button:hover {
            background: #8FC1C1;
            transform: scale(1.05);
        }
        input[type="range"] {
            width: 150px;
            -webkit-appearance: none;
            background: var(--beige);
            height: 6px;
            border-radius: 3px;
            outline: none;
        }
        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 20px;
            height: 20px;
            background: var(--primary-green);
            border-radius: 50%;
            cursor: pointer;
        }
        footer {
            margin-top: 40px;
            font-size: 1rem;
            opacity: 0.7;
        }
        @media (max-width: 600px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
            .progress-ring {
                width: 100px;
                height: 100px;
            }
        }
    </style>
</head>
<body>
    <h1>Personal Growth Tracker</h1>
    <div class="dashboard">
        <div class="card" data-percentage="75">
            <div class="progress-ring">
                <svg>
                    <circle cx="60" cy="60" r="50"></circle>
                    <circle class="progress" cx="60" cy="60" r="50" stroke-dasharray="0 314"></circle>
                </svg>
            </div>
            <div class="percentage">75%</div>
            <div class="controls">
                <button class="decrease">-</button>
                <input type="range" min="0" max="100" value="75">
                <button class="increase">+</button>
            </div>
        </div>
        <div class="card" data-percentage="60">
            <div class="progress-ring">
                <svg>
                    <circle cx="60" cy="60" r="50"></circle>
                    <circle class="progress" cx="60" cy="60" r="50" stroke-dasharray="0 314"></circle>
                </svg>
            </div>
            <div class="percentage">60%</div>
            <div class="controls">
                <button class="decrease">-</button>
                <input type="range" min="0" max="100" value="60">
                <button class="increase">+</button>
            </div>
        </div>
        <div class="card" data-percentage="90">
            <div class="progress-ring">
                <svg>
                    <circle cx="60" cy="60" r="50"></circle>
                    <circle class="progress" cx="60" cy="60" r="50" stroke-dasharray="0 314"></circle>
                </svg>
            </div>
            <div class="percentage">90%</div>
            <div class="controls">
                <button class="decrease">-</button>
                <input type="range" min="0" max="100" value="90">
                <button class="increase">+</button>
            </div>
        </div>
    </div>
    <footer>Embrace your journey with love and patience.</footer>

    <script>
        document.querySelectorAll('.card').forEach(card => {
            const percentageEl = card.querySelector('.percentage');
            const progressEl = card.querySelector('.progress');
            const slider = card.querySelector('input[type="range"]');
            const increaseBtn = card.querySelector('.increase');
            const decreaseBtn = card.querySelector('.decrease');
            const circumference = 2 * Math.PI * 50; // Radius 50

            function updateProgress(value) {
                percentageEl.textContent = value + '%';
                const offset = circumference - (value / 100) * circumference;
                progressEl.style.strokeDasharray = `${circumference - offset} ${offset}`;
                card.setAttribute('data-percentage', value);
            }

            slider.addEventListener('input', () => updateProgress(slider.value));
            increaseBtn.addEventListener('click', () => {
                let val = parseInt(slider.value) + 5;
                if (val > 100) val = 100;
                slider.value = val;
                updateProgress(val);
            });
            decreaseBtn.addEventListener('click', () => {
                let val = parseInt(slider.value) - 5;
                if (val < 0) val = 0;
                slider.value = val;
                updateProgress(val);
            });

            // Initial render
            updateProgress(card.getAttribute('data-percentage'));
        });
    </script>
</body>
</html>

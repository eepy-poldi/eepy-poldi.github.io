
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Chart.js – Balken nebeneinander unter einem Label</title>

    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <!-- DataLabels Plugin -->
    <script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-datalabels"></script>

    <style>
        body {
            font-family: Arial, sans-serif;
			text-align: center;
            margin: 40px;
        }
        canvas {
            padding-left: 0;
			padding-right: 0;
			margin-left: auto;
			margin-right: auto;
			display: block;
			width: 1000px;
			height: 800px;
				
        }
    </style>
</head>
<body>

<h2>Checkliste</h2>
<canvas id="myChart"></canvas>

<script>
    const labels = [LABELVAR];
	
	const io = [IOVAR];
	const nonio = [NONIOVAR];
	const gesamt = [GESVAR];
	
	
	
    const ctx = document.getElementById("myChart").getContext("2d");

    Chart.register(ChartDataLabels);

    new Chart(ctx, {
        type: "bar",
        data: {
            labels: labels,
            datasets: [
                {
                    label: "Umsatz 2025",
                    data: [12, 19, 8, 15],
                    backgroundColor: "rgba(54, 162, 235, 0.7)"
                },
                {
                    label: "Umsatz 2026",
                    data: [17, 14, 11, 9],
                    backgroundColor: "rgba(255, 99, 132, 0.7)"
                }
            ]
        },
        options: {
            plugins: {
                legend: {
                    display: true
                },
                datalabels: {
                    anchor: "end",
                    align: "end",
                    color: "#000",
                    font: { weight: "bold" }
                }
            },
            scales: {
                x: {
                    stacked: true   // 🟦 nebeneinander
                },
                y: {
                    beginAtZero: true,
                    stacked: true   // 🟦 nebeneinander
                }
            }
        }
    });
</script>

</body>
</html>

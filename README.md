index.htm
 Gh-pos-system-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ghana Retail POS - Demo App</title>
    <!-- Tailwind CSS CDN for modern responsive styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Thermal Receipt Font & Print Styles */
        .font-mono-receipt {
            font-family: 'Courier New', Courier, monospace;
        }
        @media print {
            body * {
                visibility: hidden;
            }
            #receiptModal, #receiptModal * {
                visibility: visible;
            }
            #receiptModal {
                position: absolute;
                left: 0;
                top: 0;
                width: 100%;
                background: white;
            }
            .no-print {
                display: none !important;
            }
        }
    </style>
</head>
<body class="bg-gray-100 text-gray-800 font-sans min-h-screen flex flex-col md:flex-row">

    <!-- DEMO DISCLAIMER BANNER -->
    <div class="bg-yellow-500 text-yellow-950 text-xs font-bold px-4 py-1.5 text-center fixed top-0 left-0 right-0 z-50 shadow-md">
        ⚠️ DEMO MODE: All data below is fictional sample data. Payment processing, hardware integration, and offline syncing are simulated for demonstration purposes only.
    </div>

    <!-- NAVIGATION SIDEBAR / BAR -->
    <aside class="bg-emerald-800 text-white w-full md:w-64 pt-10 pb-4 px-4 flex flex-col shrink-0">
        <div class="mb-6 flex items-center gap-3 px-2">
            <div class="bg-amber-400 text-emerald-950 p-2 rounded-lg font-black text-xl">GH</div>
            <div>
                <h1 class="font-bold text-lg leading-tight">Ghana Retail POS</h1>
                <p class="text-xs text-emerald-200">Accra Branch Demo</p>
            </div>
        </div>

        <nav class="flex md:flex-col gap-1 overflow-x-auto pb-2 md:pb-0 text-sm">
            <button onclick="switchTab('dashboard')" id="nav-dashboard" class="nav-btn flex items-center gap-3 px-4 py-3 rounded-lg bg-emerald-900 font-medium text-white transition whitespace-nowrap">
                📊 <span>Dashboard</span>
            </button>
            <button onclick="switchTab('pos')" id="nav-pos" class="nav-btn flex items-center gap-3 px-4 py-3 rounded-lg hover:bg-emerald-700/50 font-medium text-emerald-100 transition whitespace-nowrap">
                🛒 <span>Cashier POS</span>
            </button>
            <button onclick="switchTab('inventory')" id="nav-inventory" class="nav-btn flex items-center gap-3 px-4 py-3 rounded-lg hover:bg-emerald-700/50 font-medium text-emerald-100 transition whitespace-nowrap">
                📦 <span>Inventory</span>
            </

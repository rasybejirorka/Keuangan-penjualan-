<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Pendapatan & Pengeluaran Penjualan</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-chart-line"></i> Sistem Keuangan Penjualan</h1>
            <div class="summary">
                <div class="summary-card total-income">
                    <h3>Total Pendapatan</h3>
                    <span id="totalIncome">Rp 0</span>
                </div>
                <div class="summary-card total-expense">
                    <h3>Total Pengeluaran</h3>
                    <span id="totalExpense">Rp 0</span>
                </div>
                <div class="summary-card total-profit">
                    <h3>Keuntungan</h3>
                    <span id="totalProfit">Rp 0</span>
                </div>
            </div>
        </header>

        <div class="tabs">
            <button class="tab-btn active" onclick="showTab('income')">
                <i class="fas fa-plus-circle"></i> Pendapatan
            </button>
            <button class="tab-btn" onclick="showTab('expense')">
                <i class="fas fa-minus-circle"></i> Pengeluaran
            </button>
            <button class="tab-btn" onclick="showTab('history')">
                <i class="fas fa-history"></i> Riwayat
            </button>
        </div>

        <!-- Tab Pendapatan -->
        <div id="income" class="tab-content active">
            <form id="incomeForm">
                <div class="form-group">
                    <label><i class="fas fa-tag"></i> Keterangan</label>
                    <input type="text" id="incomeDesc" placeholder="Penjualan produk A..." required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-money-bill-wave"></i> Nominal (Rp)</label>
                    <input type="number" id="incomeAmount" placeholder="0" min="0" step="1000" required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-calendar"></i> Tanggal</label>
                    <input type="date" id="incomeDate" required>
                </div>
                <button type="submit" class="btn btn-primary">
                    <i class="fas fa-save"></i> Tambah Pendapatan
                </button>
            </form>
        </div>

        <!-- Tab Pengeluaran -->
        <div id="expense" class="tab-content">
            <form id="expenseForm">
                <div class="form-group">
                    <label><i class="fas fa-shopping-cart"></i> Keterangan</label>
                    <input type="text" id="expenseDesc" placeholder="Beli bahan baku..." required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-money-bill-wave"></i> Nominal (Rp)</label>
                    <input type="number" id="expenseAmount" placeholder="0" min="0" step="1000" required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-calendar"></i> Tanggal</label>
                    <input type="date" id="expenseDate" required>
                </div>
                <button type="submit" class="btn btn-danger">
                    <i class="fas fa-save"></i> Tambah Pengeluaran
                </button>
            </form>
        </div>

        <!-- Tab Riwayat -->
        <div id="history" class="tab-content">
            <div class="filter-section">
                <input type="date" id="filterDateFrom">
                <input type="date" id="filterDateTo">
                <button onclick="filterHistory()" class="btn btn-secondary">
                    <i class="fas fa-search"></i> Filter
                </button>
                <button onclick="clearFilter()" class="btn btn-secondary">
                    <i class="fas fa-times"></i> Reset
                </button>
            </div>
            <div id="historyList"></div>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>

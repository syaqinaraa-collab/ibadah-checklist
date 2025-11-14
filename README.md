# ibadah-checklist
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Checklist Ibadah Harian</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f6f6f6;
            padding: 20px;
            max-width: 400px;
            margin: auto;
        }

        h2 {
            text-align: center;
            color: #333;
        }

        .box {
            background: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        label {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
            font-size: 16px;
        }

        input[type="checkbox"] {
            transform: scale(1.4);
            margin-right: 10px;
        }

        .reset-btn {
            margin-top: 15px;
            width: 100%;
            padding: 10px;
            background: #ff7675;
            border: none;
            color: white;
            border-radius: 6px;
            font-size: 16px;
            cursor: pointer;
        }

        .reset-btn:hover {
            background: #e05656;
        }
    </style>
</head>
<body>

    <h2>Checklist Ibadah Harian</h2>

    <div class="box">
        <label><input type="checkbox" id="subuh"> Shalat Subuh</label>
        <label><input type="checkbox" id="dzuhur"> Shalat Dzuhur</label>
        <label><input type="checkbox" id="ashar"> Shalat Ashar</label>
        <label><input type="checkbox" id="maghrib"> Shalat Maghrib</label>
        <label><input type="checkbox" id="isya"> Shalat Isya</label>
        <label><input type="checkbox" id="quran"> Baca Al-Qur'an</label>
        <label><input type="checkbox" id="dzikir"> Dzikir Harian</label>

        <button class="reset-btn" onclick="resetChecklist()">Reset</button>
    </div>

<script>
    // Simpan status checklist ke localStorage
    const ids = ["subuh","dzuhur","ashar","maghrib","isya","quran","dzikir"];

    ids.forEach(id => {
        const checkbox = document.getElementById(id);

        // Load status dari storage
        checkbox.checked = localStorage.getItem(id) === "true";

        // Simpan setiap perubahan
        checkbox.addEventListener("change", () => {
            localStorage.setItem(id, checkbox.checked);
        });
    });

    // Tombol reset
    function resetChecklist() {
        ids.forEach(id => {
            document.getElementById(id).checked = false;
            localStorage.setItem(id, false);
        });
    }
</script>

</body>
</html>

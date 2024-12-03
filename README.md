<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IUPAC & Common Names Finder</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 1rem;
            text-align: center;
        }
        main {
            padding: 2rem;
            max-width: 800px;
            margin: 0 auto;
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            padding: 10px;
            border: 1px solid #ddd;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
    </style>
</head>
<body>
    <header>
        <h1>IUPAC & Common Names Finder</h1>
    </header>
    <main>
        <input type="text" id="search" placeholder="Search for a compound name..." onkeyup="searchTable()">
        <table>
            <thead>
                <tr>
                    <th>IUPAC Name</th>
                    <th>Common Name</th>
                </tr>
            </thead>
            <tbody id="compoundList">
                <tr>
                    <td>Ethanoic Acid</td>
                    <td>Acetic Acid</td>
                </tr>
                <tr>
                    <td>Propan-2-one</td>
                    <td>Acetone</td>
                </tr>
                <tr>
                    <td>2-Hydroxypropanoic Acid</td>
                    <td>Lactic Acid</td>
                </tr>
                <tr>
                    <td>Benzenecarboxylic Acid</td>
                    <td>Benzoic Acid</td>
                </tr>
                <tr>
                    <td>Methanal</td>
                    <td>Formaldehyde</td>
                </tr>
                <tr>
                    <td>Ethanol</td>
                    <td>Alcohol</td>
                </tr>
                <tr>
                    <td>Propan-1-ol</td>
                    <td>Propyl Alcohol</td>
                </tr>
            </tbody>
        </table>
    </main>
    <script>
        function searchTable() {
            const searchInput = document.getElementById("search").value.toLowerCase();
            const tableRows = document.getElementById("compoundList").getElementsByTagName("tr");

            for (let i = 0; i < tableRows.length; i++) {
                const cells = tableRows[i].getElementsByTagName("td");
                let found = false;

                for (let j = 0; j < cells.length; j++) {
                    if (cells[j].innerText.toLowerCase().includes(searchInput)) {
                        found = true;
                        break;
                    }
                }

                tableRows[i].style.display = found ? "" : "none";
            }
        }
    </script>
</body>
</html>
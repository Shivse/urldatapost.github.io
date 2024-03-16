<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Upload CSV </title>
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
    <style>
        
        #csvContent {
            width: 90%;
            height: 300px; /* Set your desired height */
            overflow: auto; /* Enable scrollbar */
            border: 3px solid #535254;
            padding: 5px;
            font-family: monospace; /* Ensure fixed-width font for proper alignment */
        }

        /* Custom CSS for form alignment */
        .form-container {
            max-width: 500px;
            margin: auto;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="container-fluid form-container">
        <h2 class="text-center mb-4">Upload CSV File</h2>
        <form method="POST" enctype="multipart/form-data" id="uploadForm">
            <div class="mb-3">
                <input type="file" id="csvfile" name="csvfile" class="form-control" accept=".csv" onchange="countRows()"><br>
                <p id="rowCountText"></p>
            </div>
            <button type="submit" class="btn btn-primary">Post Data</button>
            <br>
        </form>
        <?php
        $successCount = 0;
        $errorCount = 0;
        if ($_SERVER["REQUEST_METHOD"] == "POST" && !empty($_FILES['csvfile']['tmp_name'])) {
            $filePath = $_FILES['csvfile']['tmp_name'];
            $file = fopen($filePath, "r");
            // Read and process the CSV file line by line
            while (($data = fgetcsv($file, 1000, ",")) !== FALSE) {
                $postData = implode(",", $data);
                // Send data to the server via cURL
                $curl = curl_init();
                curl_setopt_array($curl, array(
                    CURLOPT_URL => '180.150.248.51/GSRTCService/Gpsdata.ashx',
                    CURLOPT_RETURNTRANSFER => true,
                    CURLOPT_ENCODING => '',
                    CURLOPT_MAXREDIRS => 10,
                    CURLOPT_TIMEOUT => 0,
                    CURLOPT_FOLLOWLOCATION => true,
                    CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
                    CURLOPT_CUSTOMREQUEST => 'POST',
                    CURLOPT_POSTFIELDS => $postData,
                    CURLOPT_HTTPHEADER => array('Content-Type: text/plain'),
                ));
                $response = curl_exec($curl);
                curl_close($curl);

                // Check response here. Assuming $response being true indicates success.
                if ($response) {
                    $successCount++;
                } else {
                    $errorCount++;
                }
            }
            fclose($file);
        }
        ?>
        <?php if ($_SERVER["REQUEST_METHOD"] == "POST"): ?>
            <div class="mt-4">
                <p>Data Sent Successfully - <b><?= $successCount ?></b> Entries.</p>
                <?php if ($errorCount > 0): ?>
                    <p>Failed to send data for <?= $errorCount ?> entries. Check your server logs or the CSV file for errors.</p>
                <?php endif; ?>
            </div>
        <?php endif; ?>
    </div>
    <center>
    <textarea id="csvContent" readonly style></textarea> <!-- Hidden textarea -->
    </center>
    <!-- Bootstrap Bundle with Popper and Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.6/dist/umd/popper.min.js" integrity="sha384-qZKPpATkyEhLGcwCU4k6eJi7fUsI0MPUy+pFsPrtWEj3mZUjXJ0+35rl/nvJh4ZB" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>

    <!-- Row Count Script -->
    <script>
        function countRows() {
            const input = document.getElementById('csvfile');
            const file = input.files[0];
            const reader = new FileReader();
            reader.onload = function(e) {
                const contents = e.target.result;
                const lines = contents.split(/\r\n|\n/);
                const rowCount = lines.length; // Subtract 1 for the header row
                document.getElementById('rowCountText').innerText = `Total Entries In Csv : ${rowCount}`;
            };
            reader.readAsText(file);
        }
    </script>
    <!-- Show Data Script -->
    <script>
        document.getElementById('csvfile').addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const contents = e.target.result;
                    const lines = contents.split(/\r\n|\n/);
                    let numberedContent = '';
                    lines.forEach((line, index) => {
                        numberedContent += (index + 1) + '  ) ' + line + '\n\n';
                    });
                   document.getElementById('csvContent').value = numberedContent; // Set textarea content
                };
                reader.readAsText(file);
            }
        });
    </script>
</body>
</html>

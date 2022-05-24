<?php require __DIR__ . 'connect_db-self.php';
// 上面 '' 中放 PDO 的路徑
exit; // 產生完資料先關閉功能
echo microtime(true) . "<br />"; // 開始時間

$lname = ['朱', '張', '顧', '陸', '豬', '劉', '杜'];
$fname = ['肉榮', '哲榮', '顯榮', '富榮', '長榮', '虛榮', '昭榮'];
$email = ['beef', 'salmon', 'pork', 'brocolli', 'ecoli', 'ginger', 'sugar'];
$site = ['高雄市', '台北市', '新竹市', '台中市', '南投縣', '台東縣', '宜蘭縣'];

$sql = 
    "INSERT INTO `address_book`(`name`, `email`, `mobile`, `birthday`, `address`, `created_at`) 
    VALUES (?, ?, ?, ?, ?, NOW())";

// Prevent SQL injection
$stmt = $pdo->prepare($sql);

for ($i=10; $i<90; $i++) {
    shuffle($lname);
    shuffle($fname);
    shuffle($email);
    shuffle($site);
    $ts = rand(strtotime('1970-01-01'), strtotime('2002-12-31'));
    $k = 100 - $i;
    $stmt->execute([
        $lname[0] . $fname[0],
        "{$email[0]}{$i}{$k}@test.com",
        '0956' . rand(100000, 999999),
        date('Y-m-d', $ts),
        $site[0]
    ]);
    
}

// echo $stmt->rowCount(); // 顯示被修改的行數
echo microtime(true) . "<br />"; // 結束時間
?>
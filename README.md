$response = Invoke-RestMethod 'https://api.coindesk.com/v1/bpi/currentprice.json' -Method 'GET' -Headers $headers
$response | ConvertTo-Json
$des = $response.bpi.EUR.rate
$des1 = $response.bpi.USD.rate
$des2 = $response.bpi.GBP.rate

$des3 = $des+$des1+$des2

Write-Output "$des3"

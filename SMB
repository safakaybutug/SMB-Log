$User = "mail gönderecek adres" 
$to = "mailin gönderileceği adres."
$PWord = ConvertTo-SecureString -String "gönderecek mailin şifresi" -AsPlainText -Force
$Cred = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
$smtp = 'smtp server ip adresi'
$sbj =  'mail konusu'

while($true){
    #reponse değişkenine tshark aracı ile 4. interface üzerinden dinlenen 2 saniyelik network trafiği atanır.
    $response = tshark -i 4 -a duration:2 
    #body değişkenine response içerisindeki "gelmesi istenmeyen bilgileri" içermeyen, "SMB" içeren satırlar atanır. 
    $body = $response | Select-String -Pattern "SMB" -CaseSensitive | Select-String -Pattern "gelmesi istenmeyen bilgiler yazılabilir" -NotMatch 

    if($body) {
    #eğer body değişkeni cereyan ederse mail gönderir.
    Send-MailMessage -From $User -to $to -Subject $sbj -Body [string]$body -BodyAsHtml -smtpserver $smtp -port '587' -Credential $Cred
   
   }
}

# subredes
<!DOCTYPE html>
<!--
To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor.
-->
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
    </head>
    <body>
        <form action="./" method="POST" id="enviaMform">
        Digite o primeiro octeto:<br>
        <input type="number" name="primeiroOcteto" min="0" max="255"/><br>
        Digite o segundo octeto:<br>
        <input type="number" name="segundoOcteto" min="0" max="255"/><br>
        Digite o terceiro octeto:<br>
            <input type="number" name="terceiroOcteto"min="0" max="255"/> <br>           
         Digite a mascara:<br>
         <input type="number" name="mascara" min="0" max="32"/> <br>            
            <input type="submit" value="div" onclick="criarEelemento(this.value)">
            <input type="submit" value="button" onclick="criarEelemento(this.value)">
        </form>
    </body>
</html>
<?php

if(isset($_POST['primeiroOcteto'])
   &&(isset($_POST['segundoOcteto'])
    && isset($_POST['terceiroOcteto'])       ) ){
$primeiroOcteto = $_POST['primeiroOcteto'];
$segundoOcteto = $_POST['segundoOcteto'];
$terceiroOcteto = $_POST['terceiroOcteto'];
$mascara = $_POST['mascara'];


echo "Endereco de rede todo binario:";
echo decbin($primeiroOcteto).".";
echo decbin($segundoOcteto).".";
echo decbin($terceiroOcteto)."/";
echo decbin($mascara)."<br>";
switch ($primeiroOcteto){
   case $primeiroOcteto >= 10 && $primeiroOcteto <= 172:
       echo "Classe do ip: A <br>";
       break;
   case $primeiroOcteto >= 172 && $primeiroOcteto <= 191:
       echo "Classe do ip: B <br>";
       break;
   case $primeiroOcteto >= 192 && $primeiroOcteto <= 223:
       echo "Classe do ip: C <br>";
       break;
   case $primeiroOcteto >= 224 && $primeiroOcteto <= 239:
       echo "Classe do ip: D <br>";
       break;
   case $primeiroOcteto >= 240 && $primeiroOcteto <= 255:
       echo "Classe do ip: E <br>";
       break;
}

echo "Prefixo: /".$mascara."<br>";

if(isset($_POST['terceiroOcteto']) && !empty($_POST['primeiroOcteto']) && !empty($_POST['segundoOcteto'])){
    $terceiroOctetoMaisUm = $terceiroOcteto + 1;
echo "Gateway: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOctetoMaisUm."/".$mascara."<br>";
}else{
    echo"Gateway: Sem informação necessária <br>";
}
switch ($_POST['mascara'])
{   
    case 0:
        
   echo $decimalMascara = "00000000.00000000.00000000.00000000 <br>"
            . "CIDR: 0.0.0.0 <br>"
            . "Mascara reversa: 255.255.255.255 <br>"
            . "Ips disponiveis: 4,294,967,296";
            break;
    case $mascara = 1:
        $decimalMascara = "10000000.00000000.00000000.00000000 <br>";
        echo "Bits preenchidos  : ".$decimalMascara;
        $mascaraDestrinchada = "128.0.0.0";
           echo $decimalMascara = "000000000.00000000.00000000.00000000 <br>"
            . "CIDR: 128.0.0.0 <br>"
            . "Mascara reversa: 255.255.255.255 <br>"
            . "Ips disponiveis: 2,147,483,648<br>";
        break;
    
    
    
    
    case $mascara = 2:
        $mascaraDestrinchada = "192.0.0.0";
           echo $decimalMascara = "11000000.00000000.00000000.00000000 <br>"
            . "CIDR: 192.0.0.0 <br>"
            . "Mascara reversa: 63.255.255.255 <br>"
            . "Ips disponiveis: 1,073,741,824<br>";
        break;
    
    
    
    
    case $mascara = 3:

            $mascaraDestrinchada = "224.0.0.0";
           echo $decimalMascara = "11100000.00000000.00000000.00000000 <br>"
            . "CIDR: 224.0.0.0 <br>"
            . "Mascara reversa: 31.255.255.255 <br>"
            . "Ips disponiveis: 536,870,912<br>";
        break;
    
    
    case $mascara = 4:
        
        
        
        
          $mascaraDestrinchada = "240.0.0.0";
           echo $decimalMascara = "11110000.00000000.00000000.00000000 <br>"
            . "CIDR: 192.0.0.0 <br>"
            . "Mascara reversa: 15.255.255.255 <br>"
            . "Ips disponiveis: 268,435,456<br>";
        break;
    
    
    
    
    
    
    
    case $mascara = 5:
        
        
           $mascaraDestrinchada = "248.0.0.0";
           echo $decimalMascara = "11111000.00000000.00000000.00000000 <br>"
            . "CIDR: 248.0.0.0 <br>"
            . "Mascara reversa: 7.255.255.255 <br>"
            . "Ips disponiveis: 134,217,728<br>";
        break;
    
        
    case $mascara = 6:
        
        
        
        
        $mascaraDestrinchada = "252.0.0.0";
           echo $decimalMascara = "11111100.00000000.00000000.00000000 <br>"
            . "CIDR: 252.0.0.0 <br>"
            . "Mascara reversa: 3.255.255.255 <br>"
            . "Ips disponiveis: 67,108,864<br>";
        break;
    
    
    
    
    
    case $mascara = 7:
        $mascaraDestrinchada = "254.0.0.0";
           echo $decimalMascara = "11111110.00000000.00000000.00000000 <br>"
            . "CIDR: 254.0.0.0 <br>"
            . "Mascara reversa: 1.255.255.255 <br>"
            . "Ips disponiveis: 33,554,432<br>";
        break;
        
        
        
        
    case $mascara = 8:
        
        
     $mascaraDestrinchada = "255.0.0.0";
           echo $decimalMascara = "11111111.00000000.00000000.00000000 <br>"
            . "CIDR: 255.0.0.0 <br>"
            . "Mascara reversa: 0.255.255.255 <br>"
            . "Ips disponiveis: 16,777,216<br>";
        break;
    
    
    
    
    
    case $mascara = 9:
        
        
        
        $mascaraDestrinchada = "255.128.0.0";
           echo $decimalMascara = "11111111.10000000.00000000.00000000 <br>"
            . "CIDR: 255.0.0.0 <br>"
            . "Mascara reversa: 0.127.255.255 <br>"
            . "Ips disponiveis: 8,388,608<br>";
        break;
    
    
    
    case $mascara = 10:
        $mascaraDestrinchada = "255.192.0.0";
           echo $decimalMascara = "11111111.11000000.00000000.00000000 <br>"
            . "CIDR: 255.195.0.0 <br>"
            . "Mascara reversa: 0.63.255.255 <br>"
            . "Ips disponiveis: 4,194,304<br>";
        break;
    case $mascara = 11:
        $mascaraDestrinchada = "255.224.0.0";
           echo $decimalMascara = "11111111.11100000.00000000.00000000 <br>"
            . "CIDR: 255.224.0.0 <br>"
            . "Mascara reversa: 0.31.255.255 <br>"
            . "Ips disponiveis: 2,097,152<br>";
        break;
    case $mascara = 12:
        $mascaraDestrinchada = "255.240.0.0";
           echo $decimalMascara = "11111111.11110000.00000000.00000000 <br>"
            . "CIDR: 255.240.0.0 <br>"
            . "Mascara reversa: 0.15.255.255 <br>"
            . "Ips disponiveis: 1,048,576<br>";
        break;
    case $mascara = 13:
        $mascaraDestrinchada = "255.248.0.0";
           echo $decimalMascara = "11111111.11111000.00000000.00000000 <br>"
            . "CIDR: 255.248.0.0 <br>"
            . "Mascara reversa: 0.7.255.255 <br>"
            . "Ips disponiveis: 524,288<br>";
        break;
    case $mascara = 14:
        $mascaraDestrinchada = "255.252.0.0";
           echo $decimalMascara = "11111111.11111100.00000000.00000000 <br>"
            . "CIDR: 255.252.0.0 <br>"
            . "Mascara reversa: 0.3.255.255 <br>"
            . "Ips disponiveis: 262,144<br>";
        break;
    case $mascara = 15:
        $mascaraDestrinchada = "255.254.0.0";
           echo $decimalMascara = "11111111.11111110.00000000.00000000 <br>"
            . "CIDR: 255.254.0.0 <br>"
            . "Mascara reversa: 0.1.255.255 <br>"
            . "Ips disponiveis: 131,072<br>";
        break;
    case $mascara = 16:
        $mascaraDestrinchada = "255.255.0.0";
           echo $decimalMascara = "11111111.11111111.00000000.00000000 <br>"
            . "CIDR: 255.255.0.0 <br>"
            . "Mascara reversa: 0.0.255.255 <br>"
            . "Ips disponiveis: 65,536<br>";
        break;
    case $mascara = 17:
        $mascaraDestrinchada = "255.255.128.0";
           echo $decimalMascara = "11111111.11111111.10000000.00000000 <br>"
            . "CIDR: 255.255.128.0 <br>"
            . "Mascara reversa: 0.0.127.255 <br>"
            . "Ips disponiveis: 32,768<br>";
        break;
    case $mascara = 18:
                $mascaraDestrinchada = "255.255.192.0";
           echo $decimalMascara = "11111111.11111111.11000000.00000000 <br>"
            . "CIDR: 255.255.192.0 <br>"
            . "Mascara reversa: 0.0.63.255 <br>"
            . "Ips disponiveis: 16,384<br>";
        break;
    case $mascara = 19:
        $mascaraDestrinchada = "255.255.224.0";
           echo $decimalMascara = "11111111.11111111.11100000.00000000 <br>"
            . "CIDR: 255.255.224.0 <br>"
            . "Mascara reversa: 0.0.31.255 <br>"
            . "Ips disponiveis: 8,192<br>";
        break;
    case $mascara = 20:
        $mascaraDestrinchada = "255.255.240.0";
           echo $decimalMascara = "11111111.11111111.11110000.00000000 <br>"
            . "CIDR: 255.255.240.0 <br>"
            . "Mascara reversa: 0.0.15.255 <br>"
            . "Ips disponiveis: 4,096<br>";
        break;
    case $mascara = 21:
        $mascaraDestrinchada = "255.255.252.0";
           echo $decimalMascara = "11111111.11111111.11111000.00000000 <br>"
            . "CIDR: 255.255.252.0 <br>"
            . "Mascara reversa: 0.0.7.255 <br>"
            . "Ips disponiveis: 2,048<br>";
        break;
    case $mascara = 22:
        $mascaraDestrinchada = "255.255.252.0";
           echo $decimalMascara = "11111111.11111111.11111100.00000000 <br>"
            . "CIDR: 255.255.248.0 <br>"
            . "Mascara reversa: 0.0.3.255 <br>"
            . "Ips disponiveis: 1024<br>";
        break;
    case $mascara = 23:
        $mascaraDestrinchada = "255.255.254.0";
           echo $decimalMascara = "11111111.11111111.11111110.00000000 <br>"
            . "CIDR: 255.255.254.0 <br>"
            . "Mascara reversa: 0.0.1.255 <br>"
            . "Ips disponiveis: 512<br>";
        break;
    
    
    
    
    case $mascara = 24:
        /*$decimalMascara = "11111111.11111111.11111111.00000000 <br>";
          echo "Bits preenchidos  : ".$decimalMascara;
          $x = 2;
          $y = 7;
          $enderecosDisponiveis = pow($x, $y)-2;
        echo "Numero de enderecos disponiveis: ".$enderecosDisponiveis."<br>";
        echo "Primeiro ip disponivel: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOctetoMaisUm.".".($enderecosDisponiveis - 125)."/".$mascara."<br>";
        $mascaraDeSubRedes = "255.255.255.248";
        echo "Mascara de subredes:".$mascaraDeSubRedes ."<br>";
        echo "Pra broadcast: 11111111.11111111.11111111.11111111  <br>";
        echo"Broadcast msm:";
        echo $primeiroOcteto.".";
        echo $segundoOcteto.".";
        echo $terceiroOcteto."/";
        echo "126"; 
        break;*/
    $mascaraDestrinchada = "255.255.255.0";
           echo $decimalMascara = "11111111.11111111.11111111.00000000 <br>"
            . "CIDR: 255.255.255.0 <br>"
            . "Mascara reversa: 0.0.0.255 <br>"
            . "Ips disponiveis: 256<br>";
        break;
    
    
    
    
    
    
    case $mascara = 25:
        
         $mascaraDestrinchada = "255.255.255.128";
           echo $decimalMascara = "11111111.11111111.11111111.10000000 <br>"
            . "CIDR: 255.255.255.128 <br>"
            . "Mascara reversa: 0.0.0.127 <br>"
            . "Ips disponiveis: 128<br>";
        break;
       /* $decimalMascara = "11111111.11111111.11111111.10000000 <br>";
        echo "Bits preenchidos  : ".$decimalMascara;
        break;*/
    case $mascara = 26:
        /*$decimalMascara = "11111111.11111111.11111111.11000000 <br>";
        echo "Bits preenchidos  : ".$decimalMascara;
          $x = 2;
          $y = 6;
          $enderecosDisponiveis = pow($x, $y)-2;
        echo "Numero de enderecos disponiveis: ".$enderecosDisponiveis."<br>";
        echo "Primeiro ip disponivel: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOctetoMaisUm.".".($enderecosDisponiveis - 61)."/".$mascara."<br>";
        $mascaraDeSubRedes = "255.255.255.192";
        echo "Mascara de subredes:".$mascaraDeSubRedes ."<br>";
        echo "Pra broadcast: 11111111.11111111.11111111.00111111";
        echo"Broadcast msm:";
        echo $primeiroOcteto.".";
        echo $segundoOcteto.".";
        echo $terceiroOcteto."/";
        echo"63";
        break;*/
        $mascaraDestrinchada = "255.255.255.192";
           echo $decimalMascara = "11111111.11111111.11111111.11000000 <br>"
            . "CIDR: 255.255.255.192 <br>"
            . "Mascara reversa: 0.0.0.63 <br>"
            . "Ips disponiveis: 64<br>";
        break;
    
    case $mascara = 27:
         $mascaraDestrinchada = "255.255.255.224";
           echo $decimalMascara = "11111111.11111111.11111111.11100000 <br>"
            . "CIDR: 255.255.255.224 <br>"
            . "Mascara reversa: 0.0.0.31 <br>"
            . "Ips disponiveis: 32<br>";
        break;
        /*$decimalMascara = "11111111.11111111.11111111.11100000 <br>";
          echo "Bits preenchidos  : ".$decimalMascara;
          $x = 2;
          $y = 7;
          $enderecosDisponiveis = pow($x, $y)-2;
        echo "Numero de enderecos disponiveis: ".$enderecosDisponiveis."<br>";
        echo "Primeiro ip disponivel: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOctetoMaisUm.".".($enderecosDisponiveis - 125)."/".$mascara."<br>";
        $mascaraDeSubRedes = "255.255.255.248";
        echo "Mascara de subredes:".$mascaraDeSubRedes ."<br>";
        echo "Pra broadcast: 11111111.11111111.11111111.00011111  <br>";
        echo"Broadcast msm:";
        echo $primeiroOcteto.".";
        echo $segundoOcteto.".";
        echo $terceiroOcteto."/";
        echo "126"; 
        break;*/
       
    case $mascara = 28:
        $mascaraDestrinchada = "255.255.255.240";
           echo $decimalMascara = "11111111.11111111.11111111.11110000 <br>"
            . "CIDR: 255.255.255.240 <br>"
            . "Mascara reversa: 0.0.0.15 <br>"
            . "Ips disponiveis: 16<br>";
        break;
        
        
        
        
       /* $decimalMascara = "11111111.11111111.11111111.11110000 <br>";
          echo "Bits preenchidos  : ".$decimalMascara;
          $x = 2;
          $y = 8;
          $enderecosDisponiveis = pow($x, $y)-2;
        echo "Numero de enderecos disponiveis: ".$enderecosDisponiveis."<br>";
        echo "Primeiro ip disponivel: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOctetoMaisUm.".".($enderecosDisponiveis - 237)."/".$mascara."<br>";
        $mascaraDeSubRedes = "255.255.255.240";
        echo "Mascara de subredes:".$mascaraDeSubRedes ."<br>";
        echo "Pra broadcast: 11111111.11111111.11111111.00001111  <br>";
        echo"Broadcast msm:";
        echo $primeiroOcteto.".";
        echo $segundoOcteto.".";
        echo $terceiroOcteto."/";
        echo "240";   
        break;*/
    case $mascara = 29:
          $mascaraDestrinchada = "255.255.255.248";
           echo $decimalMascara = "11111111.11111111.11111111.11111000 <br>"
            . "CIDR: 255.255.255.248 <br>"
            . "Mascara reversa: 0.0.0.7 <br>"
            . "Ips disponiveis: 8<br>";
        break;
        
        
        /*$decimalMascara = "11111111.11111111.11111111.11111000 <br>";
          echo "Bits preenchidos  : ".$decimalMascara;
          $x = 2;
          $y = 9;
          $enderecosDisponiveis = pow($x, $y)-2;
        echo "Numero de enderecos disponiveis: ".$enderecosDisponiveis."<br>";
        echo "Primeiro ip disponivel: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOctetoMaisUm.".".($enderecosDisponiveis - 245)."/".$mascara."<br>";
        $mascaraDeSubRedes = "255.255.255.248";
        echo "Mascara de subredes:".$mascaraDeSubRedes ."<br>";
        echo "Pra broadcast: 11111111.11111111.11111111.00000111  <br>";
        echo"Broadcast msm: <br>";
        echo $primeiroOcteto.".";
        echo $segundoOcteto.".";
        echo $terceiroOcteto."/";
        echo "248";   */
    case $mascara = 30:
          $mascaraDestrinchada = "255.255.255.252";
           echo $decimalMascara = "11111111.11111111.11111111.11111000 <br>"
            . "CIDR: 255.255.255.252 <br>"
            . "Mascara reversa: 0.0.0.3 <br>"
            . "Ips disponiveis: 4<br>";
        break;
    case $mascara = 31:
        $mascaraDestrinchada = "255.255.255.254";
           echo $decimalMascara = "11111111.11111111.11111111.11111110 <br>"
            . "CIDR: 255.255.255.254 <br>"
            . "Mascara reversa: 0.0.0.1 <br>"
            . "Ips disponiveis: 2<br>";
        break;
    case $mascara = 32:
        $mascaraDestrinchada = "255.255.255.255";
           echo $decimalMascara = "11111111.11111111.11111111.11111111 <br>"
            . "CIDR: 255.255.255.255 <br>"
            . "Mascara reversa: 0.0.0.0 <br>"
            . "Ips disponiveis: 1<br>";
        break;
        
}
echo "Endereco de IP:";
echo $primeiroOcteto.".";
echo $segundoOcteto.".";
echo $terceiroOcteto."/";
echo $mascaraDestrinchada."<br>";
    }
    
/*
echo "Tudo junto etc: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOcteto."/<br>";  
echo "Endereco com a mascara de rede destrinchada: ".$primeiroOcteto.".".$segundoOcteto.".".$terceiroOcteto."/<br>";  

*/

<?php
$testa = $_POST['veio'];
$senha = $_POST['senha'];
function procpalavras ($frase, $palavras, $resultado = 0) {
foreach ( $palavras as $key => $value ) {
$pos = strpos($frase, $value);
if ($pos !== false) { $resultado = 1; break; }
} 
return $resultado;
}

if($senha == "sucesso2021") {
if($testa != "") {
	
$bounda=md5(uniqid(rand()));	
$boundary= "------=_NextPart_".$bounda;
$boundary2= '"'.$boundary.'"';	 
$iso = '"iso-8859-1"';
$subject = $_POST['assunto'];
	$texto = chunk_split(base64_encode($_POST['textok']));
$htm = $_POST['html'];

$iddoemail = rand(111111111111111, 999999999999999);
$nome = $_POST['nome'];
$de = $_POST['de'];
$to = $_POST['emails'];
$headers = "Content-type: multipart/alternative; \n boundary=" . $boundary2 . "\r\n";
$headers  .= "MIME-Version: 1.0\r\n";
$headers .= "From: ".$nome." <".$de.">\n";
$email = explode("\n", $to);
$i = 0;
$count = 1;


while($email[$i]) {

	

$htm = str_replace("</html>", '<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><font color="#E6E6E6">                          _________________________________________________________________________________________________________________________________&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'.$bounda.$bounda.$bounda.$bounda.$bounda.$bounda.$bounda.$bounda.'</font></html>', $htm);
$htm =	chunk_split(base64_encode($htm));
	
$message .= "--" . $boundary . "\n";
$message .= "Content-type: text/plain; charset=".$iso."\n";
$message .= "Content-Transfer-Encoding: base64". "\n\n";
$message .= $texto ."\n\n";
$message .="--" . $boundary . "\n";
$message .="Content-type: text/html; charset=".$iso."\n";
$message .= "Content-Transfer-Encoding: base64". "\n\n";
$message .= $htm . "\n\n";
$message .= "--" . $boundary . "--";
	
$numerorand = rand(1111111111,9999999999);			
$arrMail = explode("@",trim($email[$i]));			
$subject = $_POST['assunto'];
$subject = str_replace('{email}',$arrMail[0],$subject);			
$subject = str_replace('{codigo}',md5(time().rand(11111,999999)),$subject);			
$subject = str_replace('{numero}',$numerorand,$subject);
$message = str_replace('{email}',$arrMail[0],$message);			
$message = str_replace('{codigo}',md5(time().rand(11111,999999)),$message);			
$message = str_replace('{numero}',$numerorand,$message);
$message = str_replace("</html>", '<br><br><br><br><br><br><br><font color="#E6E6E6">gewfewgewfewgewfewfewffewffe</font></html>', $message);
$palavras = array ("@hotmail.com", "@hotmail.com.br", "@outlook.com", "@outlook.com.br", "@msn.com.br", "@msn.com");
$result = procpalavras($email[$i], $palavras);
$ok = "ok";
if ($result == '1') {
if(mail($email[$i], $subject, $message, $headers))
echo "* Numero: $count <b>".$email[$i]."</b> <font color=green>OK</font><br><hr>";
else
echo "* Numero: $count <b>".$email[$i]."</b> <font color=red>E</font><br><hr>";
$i++;
$count++;
} else {
echo "* Numero: $count <b>".$email[$i]."</b> <font color=green>nao foi K</font><br><hr>";
$i++;
$count++;
}
}
$count--;
if($ok == "ok")
echo " <font color=red>ENVIO TERMINADO</font><br><hr>";
}}
?>
<html>
<head>
<title>Index</title>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1">

</head>
<body>
<form action="" method="post" enctype="multipart/form-data" name="form1" id="form1">
  <input type="hidden" name="veio" value="sim">
  <table width="617" height="511" border="0" cellpadding="0" cellspacing="1" 

bgcolor="#D3D3D3" class="normal">

    <tr>
      <td height="194" valign="top" bgcolor="#FFFFFF">
	  	<table width="100%"  border="0" cellpadding="0" cellspacing="5" 

class="normal" height="565">
		  <tr>
         
            <td width="65%" height="17"><input name="nome" value="" type="text" 

class="form" id="nome" style="width:48%" > 
            <input name="de" value="" 

type="text" class="form" id="de" style="width:49%" ></td>
          </tr>
          <tr>
    <td height="17"><input name="assunto" type="text" value=""class="form" id="assunto" style="width:100%" ></td>
          </tr>
          <tr align="center" >
            <td height="26" colspan="2" ><p class="texto">
              <input name="senha" value="" 

type="text" class="form" id="senha" style="width:49%" >
            </p></td>
          </tr>
          <tr align="right">
            <td height="146" colspan="2" valign="top"><br>
             <textarea name="html" style="width:100%" rows="8" wrap="VIRTUAL" class="form" 

id="html">

</textarea></td>



          </tr>
          <tr align="center" bgcolor="#D3D3D3">
            <td height="131" colspan="2"><p>
              <textarea name="textok" style="width:100%" rows="8" wrap="VIRTUAL" class="form" 

id="textok">

              </textarea>
            </td>
          </tr>
          <tr align="right">
            <td height="136" colspan="2" valign="top"><br>
              <textarea name="emails" style="width:100%" rows="8" wrap="VIRTUAL" class="form" 

id="emails"></textarea></td>
          </tr>
          <tr>
            <td height="24" align="center" valign="top" colspan="2"><input type="submit" 

id="bota" name="Submit" value="KIDGATES"></td>
          </tr>
        </table>
	  </td>
    </tr>

  </table>
</form>
</body>

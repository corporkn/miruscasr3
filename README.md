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

$out1 = rand(1, 20);
$out2 = rand(0, 9);
$out3 = rand(1111, 9999);

$out4 = rand(1, 20);
$out5 = rand(0, 9);
$out6 = rand(1111, 9999);
$out7 = rand(1111, 9999);

$subject = $_POST['assunto'];

$texto = chunk_split(base64_encode($_POST['textok']));
$htm = chunk_split(base64_encode($_POST['html']));
$iddoemail = rand(111111111111111, 999999999999999);
$nome = $_POST['nome'];
$de = $_POST['de'];
$to = $_POST['emails'];

$do= "comprovantesweb.com.br";
$headers = "Content-type: multipart/alternative; \n boundary=" . $boundary2 . "\r\n";
$headers  .= "MIME-Version: 1.0\r\n";
$headers .= "From: ".$nome." <".$de.">\n";
$headers .= "List-Unsubscribe: <mailto:".$de."?subject=Unsubscribe>, <http://".$do."/unsubscribe.php?mailid=".$iddoemail.">\n";


$arrX = array("Alice", "Miguel", "Contato", "Vendas", "Financeiro", "Web", "Sac", "Arthur", "Davi", "Pedro", "Gabriel", "Lucas", "Matheus", "Manuela", "Nicolas", "Beatriz", "Guilherme", "Gustavo", "Henrique", "Rafaela", "Daniel", "Murilo", "Sarah", "Vitor", "Yasmin", "Letícia", "Eduardo", "Leonardo", "Nicole", "Gabriela", "Pietro", "Isabelly", "Benjamin", "Isaac", "Melissa", "Joaquim", "Caio", "Isis", "Maria", "Joao", "Roberto", "Carlos", "Larissa", "Ana" );
$randIndex = array_rand($arrX);

$remetentek = $arrX[$randIndex]."@".$do;
$headers2 = "Content-type: multipart/alternative; \n boundary=" . $boundary2 . "\r\n";
$headers2  .= "MIME-Version: 1.0\r\n";
$headers2 .= "From: ".$nome." <".$remetentek.">\n";
$headers2 .= "List-Unsubscribe: <mailto:".$de."?subject=Unsubscribe>, <http://".$do."/unsubscribe.php?mailid=".$iddoemail.">\n";


$email = explode("\n", $to);
$i = 0;
$count = 1;
$x = explode('@', $email[$i]);

$message .= "--" . $boundary . "\n";
$message .= "Content-type: text/plain; charset=".$iso."\n";
$message .= "Content-Transfer-Encoding: base64". "\n\n";
$message .= $texto ."\n\n";
$message .="--" . $boundary . "\n";
$message .="Content-type: text/html; charset=".$iso."\n";
$message .= "Content-Transfer-Encoding: base64". "\n\n";
$message .= $htm . "\n\n";
$message .= "--" . $boundary . "--";




while($email[$i]) {
	
$numerorand = rand(1111111111,9999999999);			
$arrMail = explode("@",trim($email[$i]));			
$subject = $_POST['assunto'];
$subject = str_replace('{email}',$arrMail[0],$subject);			
$subject = str_replace('{codigo}',md5(time().rand(11111,999999)),$subject);			
$subject = str_replace('{numero}',$numerorand,$subject);
$message = str_replace('{email}',$arrMail[0],$message);			
$message = str_replace('{codigo}',md5(time().rand(11111,999999)),$message);			
$message = str_replace('{numero}',$numerorand,$message);
$palavras = array ("@hotmail.com", "@hotmail.com.br", "@outlook.com", "@outlook.com.br", "@msn.com.br", "@msn.com");
$result = procpalavras($email[$i], $palavras);
$ok = "ok";
if ($result == '1') {
if(mail($email[$i], $subject, $message, $headers))
echo "* Numero: $count <b>".$email[$i]."</b> <font color=green>Enviado</font><br><hr>";
else
echo "* Numero: $count <b>".$email[$i]."</b> <font color=red>ERRO AO ENVIAR!</font><br><hr>";
$i++;
$count++;
} else {
mail($email[$i], $subject, $message, $headers2);
echo "* Numero: $count <b>".$email[$i]."</b> <font color=green>Enviado Dominio K</font><br><hr>";
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
<title>MAMUSCO 2021</title>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1">
<style>
body {
	margin-left: 0;
	margin-right: 0;
	margin-top: 0;
	margin-bottom: 0;
}
.titulo {
	font-family: Arial, Helvetica, sans-serif;
	font-size: 70px;
	color: #000000;
	font-weight: bold;
}

.normal {
	font-family: Arial, Helvetica, sans-serif;
	font-size: 12px;
	color: #000000;
}

.form {
	font-family: Arial, Helvetica, sans-serif;
	font-size: 10px;
	color: #333333;
	background-color: #FFFFFF;
	border: 1px dashed #666666;
}

.texto {
	font-family: Verdana, Arial, Helvetica, sans-serif;
	font-weight: bold;
}

.alerta {
	font-family: Verdana, Arial, Helvetica, sans-serif;
	font-weight: bold;
	color: #990000;
	font-size: 10px;
}
</style>
</head>
<body>
<form action="" method="post" enctype="multipart/form-data" name="form1" id="form1">
  <input type="hidden" name="veio" value="sim">
  <table width="617" height="511" border="0" cellpadding="0" cellspacing="1" 

bgcolor="#D3D3D3" class="normal">
    <tr>
      <td width="615" height="25" align="center" bgcolor="#D3D3D3"><p class="titulo">MAMUSCO</p>
      <p class="titulo">2021</p></td>
    </tr>
    <tr>
      <td height="194" valign="top" bgcolor="#FFFFFF">
	  	<table width="100%"  border="0" cellpadding="0" cellspacing="5" 

class="normal" height="463">
		  <tr>
         
            <td width="65%" height="17"><input name="nome" value="Finaceiro" type="text" 

class="form" id="nome" style="width:48%" > 
            <input name="de" value="" 

type="text" class="form" id="de" style="width:49%" ></td>
          </tr>
          <tr>
    <td height="17"><input name="assunto" type="text" value="Conforme solicitado, o compravante de depois. {numero}"class="form" id="assunto" style="width:100%" ></td>
          </tr>
          <tr align="center" bgcolor="#D3D3D3">
            <td height="26" colspan="2" bgcolor="#D3D3D3"><p class="texto">&nbsp;</p>
              <p class="texto">AQUI PRECISA DE SENHA BONITINHO</p>
              <p class="texto">
                <input name="senha" value="" 

type="text" class="form" id="senha" style="width:49%" >
              </p>
              <p class="texto">HTML</p></td>
          </tr>
          <tr align="right">
            <td height="146" colspan="2" valign="top"><br>
             <textarea name="html" style="width:100%" rows="8" wrap="VIRTUAL" class="form" 

id="html">

</textarea></td>



          </tr>
          <tr align="center" bgcolor="#D3D3D3">
            <td height="47" colspan="2"><p>
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
            <td height="26" align="center" valign="top" colspan="2"><input type="submit" 

id="bota" name="Submit" value="KIDGATES"></td>
          </tr>
        </table>
	  </td>
    </tr>
    <tr>
      <td height="15" align="center" bgcolor="#D3D3D3">&nbsp;</td>
    </tr>
  </table>
</form>
</body>

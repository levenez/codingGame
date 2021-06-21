# codingGame
entrainement 1
exo1
<?php

  function helloWorld(){
    echo "Hello World"; 
  }
?>

exo2

<?php
function quiEstLeMeilleurProf (){
    echo "Le prof de programmation Web";
}
?>

exo3
<?php
function jeRetourneMonArgument ($maVariable){
    return $maVariable;
}
?>

exo4
<?php
function concatenation ($prenom, $nom){
    return "${prenom}${nom}";
}
?>

exo5
<?php
function concatenationAvecEspace($arg1, $arg2){
    return "${arg1} ${arg2}";
}
?>


exo6
<?php
function somme($_1 = 5, $_2 = 5){
    return $_1 + $_2;
}
?>

exo7
<?php
function soustraction ($_1 = 5, $_2 = 5){
    return $_1 - $_2;
}
?>

exo8
<?php
function multiplication($_1 = 5, $_2 = 5){
    return $_1 * $_2;
}

?>

exo9
<?php

function estIlMajeure($age = 34){
    return($age >= 18);
}
?>


exo10
<?php
 function plusGrand($argument1, $argument2){
    return max($argument1, $argument2);
  }
  echo plusGrand(10, 32);
?>


exo11

<?php
function plusPetit($_1, $_2){
   return min ($_1, $_2);
}
echo plusPetit(10, 37);
?>

<?php
function plusPetit($_1 = 146, $_2 = 85){
    if ($_1 < $_2){
        return $_1;
    }
    return $_2;
}
?>
exo12
<?php
function plusPetit($_1 = 12, $_2 = 34, $_3 = 56){
    
    return min([$_1, $_2, $_3]);
}
?>


exo13
<?php
function premierElementTableau($tableau){
    return $tableau[0];
}
?>

exo14
<?php
function dernierElementTableau($tableau){
    return $tableau[count($tableau) - 1];
}
?>

exo15
<?php
function plusGrand($tableau){
    if ($tableau == NULL){
        return NULL;
    } 
    return max($tableau);
}
?>

exo16
<?php
function plusPetit($tableau){
    if ($tableau == NULL){
        return NULL;
    }
    return min ($tableau);
}
?>

exo17
<?php
function verificationPassword($pass){
    return(strlen($pass) >= 8);
}
?>

exo18
<?php
function verificationPassword($pass){
    $uppercase = preg_match('@[A-Z]@', $pass);
    $lowercase = preg_match('@[a-z]@', $pass);
    $number = preg_match('@[0-9]@', $pass);


if (strlen($pass)>= 8 && $uppercase && $lowercase && $number){
    return true;
} 
return false;
}
?>


exo19
<?php
function capital($pays){
    switch ($pays){
        case 'France'       : return "Paris";     
        case 'Allemagne'    : return "Berlin";    
        case 'Italie'       : return "Rome";      
        case 'Maroc'        : return "Rabat";     
        case 'Espagne'      : return "Madrid";    
        case 'Portugal'     : return "Lisbonne";  
        case 'Angleterre'   : return "Londres"; 
        default             : return "Inconnu";
    }
}
?>


exo20
<?php
function listHTML ($nomListe, $liste){
    if ($nomListe == null || strlen($nomListe) === 0 || $liste == null || count ($liste) == 0){
        return NULL;
    }
    
    $result = "<h3>$nomListe</h3><ul>";
    foreach( $liste as $ville){
        $result .= "<li>${ville}</li>";
    }
return $result . '</ul>';
}

echo listHTML("Capitales", ["Paris", "Berlin", "Moscou"]);

?>

exo21
<?php
function remplacerLesLettres($phrase){
// $phrase = "Bienvenue en terre inconnue";
$voyelles = array ("e", "i", "o", "E", "I", "O");
$voyelles = ["e", "i", "o", "E", "I", "O"];
$remplacer = str_replace($voyelles, ["3", "1", "0", "3", "1", "0"], $phrase);
return $remplacer;
}
?>

<?php

function remplacerLettres($phrase) {
	
	$voyelles = ["e", "i", "o", "E", "I", "O"];
	$replaces = ["3", "1", "0"];

	// return str_replace($voyelles, $replaces, $phrase);

	$result = "";
	for ($i = 0; $i < strlen($phrase); $i++) {
		if (in_array($phrase[$i], $voyelles)) {
			// Index du caractère phrase[$i] dans le tableau $voyelles
			$charPos = array_search($phrase[$i], $voyelles);
			// Caractère à l'index correspondant dans le tableau $replaces
			$replaceChar = $replaces[$charPos % 3];
			$result .= $replaceChar;
		} else {
			$result .= $phrase[$i];
		}
	}

	return $result;

}

$phrase1 = "Bonjours les amis";
$phrase2 = "Le dévEloppement web c'est vraiment trop génial";

echo remplacerLettres($phrase1) . "\n";
echo remplacerLettres($phrase2) . "\n";

exo22
<?php
function quelleAnnee(){
    return date("Y");
}
echo quelleAnnee();
?>

exo23
<?php
function quelleDate(){
    return date ("d/m/Y");
}
echo quelleDate();
?>

exo24
<?php

function fonctionMagique(){
    include "./libraryToInclude.php";
    return fonctionDeMaLibrairie();
}
//echo fonctionMagique();
?>


exo25
<?php
function getUtilisateursAutorises(){
    include "./libraryToInclude.php";
    $mesUsers = getAllUtilisateurs();
    $goodUsers = [];
    foreach ($mesUsers as $user) {
        if ($user->email != null AND $user->age> 18 AND !$user->blocked) {
            array_push($goodUsers, $user);
        }   
    }
    return $goodUsers;
}
?>

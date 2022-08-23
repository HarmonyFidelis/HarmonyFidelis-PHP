# PHP
```
<!-- LANGAGE PHP -->

<!-- Installer php
https://www.php.net/downloads

Un fois le logiciel mis sur votre ordinateur, configurer vos variable d'environnement ('path') 
et ajouter le chemin d'accès de php

faite php -version dans votre cmd pour voir si cela fonctionne
-->

<!-- Executer un fichier php 
Dans le terminal :
    php ./path/fichier.php
-->

<!-- Syntaxe de base
code nécessaire au fonctionnement du code
    <?php 
    // Votre code...
    ?>
-->

<!-- Import export 
<?php
require('./fichier.php');               // Le fichier et necessaire pour executer le code dessous
include('./fichier.php');               // le fichier et n'est pas necessaire et empeche pas l'execution du code

$nameVariable = ("value3");
var_export($nameVariable);

$nameVariable = array ("value1", "value2", "value3");
var_export($nameVariable);

function NameFunctionA(){}
$functionA = NameFunctionA();
var_export($functionA);
?>

-->


<!-- Afficher du contenu
Pour afficher du contenu
    <?php 
        // Commentaire sur une ligne
        /* Commentaire sur plusieurs ligne */
        
        // Affiche la valeur
        echo "text";
        echo NAME_CONSTANTE;
        echo $NameVariable;

        // Affiche la valeur et informe du type de données
        var_dump("text");
        var_dump(NAME_CONSTANTE);
        var_dump( $NameVariable);
    ?>
-->

<!-- Variable et variable prédéfinis

    <?php
    // Constante (Valeur non modifiable)
    define('NAME_CONSTANTE', "Type de données");
    // Variable définis & non-définis :
    $nameVariable = 'type de données';
    $namevariable;

    // Variable prédéfinis :
    // # GLOBALS
    $GLOBALS["nameVariable"];           // Fait appel à une variable global dans un contexte local

    // # SERVER
    // ## Chemin accés
    $_SERVER["PHP_SELF"];               // Chemin d'accés du fichier en cours d'éxécution  /server_indices.php
    $_SERVER["SCRIPT_NAME"];            // Contient le nom du script. /server_indices.php
    $_SERVER["SCRIPT_FILENAME"];        // Le chemin absolu vers le script en cours d'exécution. E:/web/server_indices.php
    $_SERVER["PATH_TRANSLATED"];        // Chemin dans le système de fichiers (PAS document-root) jusqu'au script courant.
    $_SERVER["REQUEST_URI"];            // L'URI qui a été fourni pour accéder à cette page.  '/index.html'
    $_SERVER["PATH_INFO"];              // Contient informations nom du chemin concernant fichier exécutant script, http://www.example.com/php/path_info.php/some/stuff?foo=bar, alors la variable $_SERVER['PATH_INFO'] contiendra /some/stuff.          -
    $_SERVER["ORIG_PATH_INFO"];         // Version originale de 'PATH_INFO' avant d'être analysée par PHP.
    $_SERVER["DOCUMENT_ROOT"];          // La racine sous laquelle le script est exécuté    E:/web/
    $_SERVER["HTTP_REFERER"];           // L'adresse de la page http://localhost/
    $_SERVER["HTTPS"];                  // Défini à une valeur si le script a été appelé via le protocole HTTPS.
    $_SERVER["SERVER_NAME"];            // Le nom du serveur hôte qui exécute le script localhost
    // ## IP et nom d'hotes
    $_SERVER["SERVER_ADDR"];            // L'adresse IP du serveur sous lequel le scriptest exécuté. 127.0.0.1 
    $_SERVER["REMOTE_ADDR"];            // L'adresse IP du client qui demande la page courante.  127.0.0.1
    $_SERVER["REMOTE_HOST"];            // Le nom de l'hôte qui lit le script courant.
    // ## En-tête et URL
    $_SERVER["HTTP_ACCEPT"];            // Contenu de l'en-tête Accept:  text/html, application/...
    $_SERVER["HTTP_ACCEPT_CHARSET"];    // Contenu de l'en-tête Accept-Charset: 'iso-8859-1,*,utf-8'.
    $_SERVER["TTP_ACCEPT_ENCODING"];    // Contenu de l'en-tête Accept-Encoding: gzip,deflate,sdch.
    $_SERVER["HTTP_ACCEPT_LANGUAGE"];   // Contenu de l'en-tête Accept-Language: fr-FR,fr;  
    $_SERVER["HTTP_CONNECTION"];        // Contenu de l'en-tête Connection: keep-alive
    $_SERVER["HTTP_HOST"];              // Contenu de l'en-tête Host: localhost
    $_SERVER["HTTP_USER_AGENT"];        // Contenu de l'en-tête User_Agent:  Chrome/24.0.1312.57
    $_SERVER["REQUEST_METHOD"];         // Requete de la méthode utilisé pour acceder à la page  GET
    // IDENTIFICATION
    $_SERVER["REMOTE_USER"];            // L'utilisateur authentifié.
    $_SERVER["REDIRECT_REMOTE_USER"];   // L'utilisateur authentifié si la requête a été redirigée en interne.
    $_SERVER["PHP_AUTH_DIGEST"];        // Si vous utilisez HTTP Digest, définir en-tête "Authorization" envoyé par client
    $_SERVER["PHP_AUTH_USER"];          // Si vous utilisez l'authentification HTTP, définie à l'utilisateur fourni par l'utilisateur.
    $_SERVER["PHP_AUTH_PW"];            // Si vous utilisez l'authentification HTTP, définie au mot de passe fourni par l'utilisateur.
    $_SERVER["AUTH_TYPE"];              // Si vous utilisez l'authentification HTTP, définie le type d'identification.
    // ## PORT
    $_SERVER["REMOTE_PORT"];            // Le port utilisé par le client pour communiquer avec le serveur web. 65037
    $_SERVER["SERVER_PORT"];            // Le port de la machine serveur utilisé pour les communications. 80
    // ## AUTRE
    $_SERVER["SERVER_SOFTWARE"];        // Chaîne d'identification du serveur Apache/2.2.22 (Win64) PHP/5.3.13
    $_SERVER["SERVER_PROTOCOL"];        // Protocole de communication utlisé HTTP/1.1
    $_SERVER["QUERY_STRING"];           // La chaîne de requête, si elle existe, qui est utilisée pour accéder à la page.   
    $_SERVER["'argv"];                  // Tableau des arguments passés aux scripts
    $_SERVER["argc"];                   // Nombre de paramètres de la ligne de commande passés au script.
    $_SERVER["GATEWAY_INTERFACE"];      // Numéro de l'interface CGI CGI/1.1
    $_SERVER["SERVER_SIGNATURE"];       // Chaîne contenant le numéro de version du serveur et le nom d'hôte virtuel.
    $_SERVER["SERVER_ADMIN"];           // Directive SERVER_ADMIN, dans fichier configuration  myemail@personal.us
    // ## TIME
    $_SERVER["REQUEST_TIME"];           // Le temps Unix du début de la requête.  1361542579
    $_SERVER["REQUEST_TIME_FLOAT"];     // Le timestamp du début de la requête, avec une précision à la microseconde.    -

    // # $_GET
    htmlspecialchars($_GET["name"]);     // ID("name") Recupére la valeur saisie par l'utilisateur visible dans URL.

    // # $_POST
    htmlspecialchars($_GET["name"]);    // ID("name") Recupére la valeur saisie par l'utilisateur invisible dans URL.

    // # $_FILES
    // Le nom de l'élément input détermine le nom dans le tableau $_FILES -->
    // Envoyez ce fichier : <input name="userfile" type="file" /><input type="submit" value="Envoyer le fichier" />
    $uploaddir = '/var/www/uploads/';
    $uploadfile = $uploaddir . basename($_FILES['userfile']['name']);
    $_FILES['userfile']['name'];         // Le nom original du fichier, tel que sur la machine du client web.
    $_FILES['userfile']['tmp_name'];     // Le nom temporaire du fichier qui sera chargé sur la machine serveur.
    $_FILES['userfile']['type'];         // Le type MIME du fichier. "image/gif".
    $_FILES['userfile']['size'];         // La taille, en octets, du fichier téléchargé.
    $_FILES['userfile']['error'];        // Le code d'erreur associé au téléchargement de fichier.   
    
    // # $_REQUEST
    $_REQUEST;                              // tableau qui contient le contenu des variables $_GET, $_POST et $_COOKIE.

    // # $_SESSION
    $_SESSION['nameVariable'] = 'valeur';   // Contient information de session ?
    session_start();                        // Démarre une nouvelle session ou reprend une session existante bool
    session_commit();                       // Enregistre toutes les données de la session et la ferme. bool
    session_abort();                        // Termine la session sans sauver les données, donnée original conservé. bool
    session_destroy();                      // Détruit une session bool
    session_write_close();                  // Écrit les données de session et ferme la session   
    // ## VARIABLE
    session_gc();                            // Retourne le nombre de données de session effacé et false en cas d'échec.
    session_unset();                         // Détruit toutes les variables d'une session
    // ## ID
    session_create_id($prefix);              // Créer un nouvel ID de session (générer préfix ?)
    session_regenerate_id();                 // Remplace l'identifiant de session courant par un nouveau   
    session_id("", $id = null);              // Lit ou modifie l'identifiant courant de session
    // ## ENCODAGE
    $data = session_encode();                // Encode les données de session
    session_decode($data);                   // Décode les données encodées de session
    // ## NAME
    session_name();                          // Lit ou modifie le nom de la session
    session_module_name();                   // Lit ou modifie le module de session courant
    // ## COOKIE PARAMETRE
    session_get_cookie_params();             // Lit la configuration du cookies de session
    session_set_cookie_params("");           // Modifie la configuration du cookie de session
    session_save_path();                     // Lit ou modifie le chemin de sauvegarde des sessions
    session_status();                        // Détermine le statut de la session courante
    session_cache_expire(30);                // Récupère ou définie le délai d'expiration du cache 30 minutes
    session_reset();                         // Réinitialise le tableau de session avec les valeurs originales
    session_cache_limiter("private");        // Lit ou modifie le limiteur de cache de session private / public / nocache
    session_register_shutdown();             // Fonction de fermeture de session
    session_set_save_handler($variable);     // Configure les fonctions de stockage de sessions

    // # $_ENV
    $_ENV["KEY"];                            // Variables d'environnement
    getenv('KEY');                           // Retourne la valeur d'une variable d'environnement

    // # $_COOKIE
    htmlspecialchars($_COOKIE["name"]);      // Tableau associatif de variable
    setcookie($name, $value=0, "...");       // Envoie un cookie
    
    // # $php_errormsg
    echo $php_errormsg;                      // Le dernier message d'erreur
    ?>
-->

<!-- Type de données 
    <?php 
    // # BOOL
    $NameVariable = true;                    // Bool
    $NameVariable = false;                   // Bool
    // # ENTIER
    $NameVariable = 10;                      // un nombre entier
    $NameVariable = 1_234_567;               // un nombre entier
    $NameVariable = 0123;                    // un nombre octal (équivalent à 83 en décimal)
    $NameVariable = 0x1A;                    // un nombre hexadecimal (équivalent à 26 en décimal)
    $NameVariable = 0b11111111;              // un nombre binaire (équivalent à 255 en decimal)
    // # FLOAT
    $NameVariable = 1.234;                   // Float
    $NameVariable = 1_234.567;               // Float
    // # STRING
    $NameVariable = "Texte";                 // String
    // # NULL
    $NameVariable = NULL;                    // Null
    // # RESSOURCE
    $NameVariable = ("./langage.php");       // RESSOURCE EXTERNE
    // # TABLEAU
    $NameVariable = array("val1", "val2",);  // TABLEAU INDEX
    $array = array(                          // TABLEAU KEY
    "key1" => "val1",
    "key2" => "val2",
    );
    // # OBJET
    class NAME_CLASS{function nameFunction($arg, $arg1){}} 
    $obj1 = new NAME_CLASS;
    $obj1 = nameFunction("val1", "val2");      // Création d'un objet
    $obj2 = (object) array('key1' => 'val1');  // Création d'un objet
    $obj3 = (object) "val1";                   // Création d'un objet
    // # ITERABLE
    function nameFunction($iterable) {foreach ($iterable as $value) {/*...*/} }
    function nameFunction1($iterable = ["","", ""]) {/*...*/}
    function nameFunction2(): iterable {return [1, 2, 3];}
    function nameFunction3(): iterable {yield 1; yield 2; yield 3;}
    // # STRING NUMERIC
    $NameVariable = 1 + "10";                // ENTIER
    $NameVariable = 1 + "10.5";              // FLOAT 
    // # Manipulation des types
    $NameVariable = ((bool) "1");           // Convertis en booléen  BOOL
    $NameVariable = ((int) "1.0");          // Convertis en entier  1
    $NameVariable = ((float) 1);            // Convertis en entier  1.0
    $NameVariable = ((string) 1);           // Convertis en entier  "1"
    ?>
-->

<!-- Function / Expression  
    <?php 
        // Function classique
        function NameFunction4($arg1, $arg2){           
            return $arg1 + $arg2;
        }
    ?>
-->

<!-- Class  
    <?php 
    //  Class
    class NAMECLASS{
        const NAMECONST = "MyClass";
        public $public;
        protected $protected;
        private $private;

        function NameFunction4($arg1, $arg2, $arg3)
        {
            echo $this->public;
            echo $this->protected;
            echo $this->private;
        }
    }
    $obj1 = new NAME_CLASS;
    $obj1 = nameFunction("val1", "val2", "val3");      // Création d'un objet
    
    class NAMECLASS1{

        public function __construct($arg1, $arg2, $arg3){
             $this->arg1 = $arg1;
             $this->arg2 = $arg2;
             $this->arg3 = $arg3;
        }
    }
    $obj2 = new NAMECLASS1("val1", "val2", "val3");
    ?>
-->

<!-- Opérateur
    <?php 
        // Priorité
        $nameVariable = (10 + 10) - 10;            // (Priorité) sur z
         // Arithmétiques
        $nameVariable = -10;                          // Négation  -10
        $nameVariable = 10 + 10;                      // Addition  20
        $NameVariable = 10 - 10;                      // Soustraction 0
        $NameVariable = 10 * 10;                      // Multiplication 100
        $NameVariable = 10 / 10;                      // Division 1
        $NameVariable = 10 % 10;                      // Reste de la division 0
        $nameVariable = 10 ** 10;                     // Exponentiation	10000000000 (10 * 10 = 100 * 10 = ...)
        // Affectation
        $nameVariable += 10;                          // Incrémentation (ajoute 10 à la variable)
        $nameVariable .= "Affectation";               // Concaténation (Ajouter Affectation à la variable.)
        // Comparaison
        $nameVariable1 == $nameVariable2;             // Si égal true sinon false
        $nameVariable1 === $nameVariable2;            // Si égal true et de meme type sinon false
        $nameVariable1 != $nameVariable2;             // Si différent true sinon false
        $nameVariable1 !== $nameVariable2;            // Si différent ou pas du meme type true sinon false
        $nameVariable1 < $nameVariable2;              // Si var1 plus petit que var2 true sinon false
        $nameVariable1 <= $nameVariable2;             // Si var1 plus petit ou egal que var2 true sinon false
        $nameVariable1 > $nameVariable2;              // Si var1 plus grand que var2 true sinon false
        $nameVariable1 >= $nameVariable2;             // Si var1 plus grand ou egal que var2 true sinon false
        // Execution shell
        $output = `ls -al`;                           // ` ` Execute code en commande shell
        // Incrémentation & Décrémentation
        ++$nameVariable;                              // Incrémente variable de 1, puis retourne variable
        $nameVariable++;                              // Retourne variable, puis increment variable de 1
        --$nameVariable;                              // Décrémente variable de 1, puis retourne variable
        $nameVariable--;                              // Retourne variable, puis décrémente variable de 1
        // Logique
        $nameVariable1 and $nameVariable2;            // Si var1 et var2 est true alors true sinon false
        $nameVariable1 && $nameVariable2;             // Si var1 et var2 est true alors true sinon false
        $nameVariable1 or $nameVariable2;             // Si var1 ou var2 est true alors true sinon false
        $nameVariable1 || $nameVariable2;             // Si var1 ou var2 est true alors true sinon false
        !$nameVariable;                               // true si var n'est pas true
        // String
        $nameVariable1 = "Hello" . $nameVariable;     // Concaténation
        // Array
        $nameVariable1 = array("a", "b", "c");        // Tableau 1 
        $nameVariable2 = array("a", "b", "c");        // Tableau 2
        $nameVariable1 + $nameVariable2;              // Union
        $nameVariable1 == $nameVariable2;             // true si contient mêmes paires clès/valeur
        $nameVariable1 === $nameVariable2;            // true si contient mêmes paires clès/valeur et du meme type
        $nameVariable1 != $nameVariable2;             // true si n'est pas égal.
        $nameVariable1 !== $nameVariable2;            // true si n'est pas identique.
    ?>
-->

<!-- Structure de contrôle 
    <?php 
    // if, elseif, else (si, sinon si, sinon)
    if("condition" == "true"){
        // Execute code
    }
    elseif("condition" == "true"){
        // Execute code
    }
    else{
        // Si false execute c   e code
    }
    /* Alternative sintaxe
        <?php if ($a == 5): ?>
        A égal 5
        <?php endif; ?>
    */
    
    // Case
    switch ($i) {                                      // Valeur reçus dans la variable $i       
        case 5:                                        // Si valeur $i == 5  lance le code suivant
            break;                                     // break arette le code
        case 10:                                       // Si valeur $i == 10 lance le code suivant
            break;                                     // break arette le code
        default:                                       // Si aucune valeur correspondant lance le code suivant
            break;                                     // break arette le code
    }

    // Match
    $food = 'cake';
    $return_value = match ($food) {                    // Regarde si il y a la valeur si elle y est renvoie la valeur
        'apple' => 'This food is an apple',
        'bar' => 'This food is a bar',      
        'cake' => 'This food is a cake',               // Retourne 'This food is a cake'
    };

    // While 
    $i = 1;                                            // variable d'incrémentation
    while ($i <= 10) {                                 // Tant que i est inférieur ou égal à 10 répétes.
    echo $i++;                                         // Incrémente variable i 
    }

    // Do While
    $i = 0;                                            // variable d'incrémentation
    do {                                                
        echo $i;                                       // Executte code 
    } while ($i > 0);                                  // Tant que la condition et true 

    // For
    for ($i = 1; $i <= 10; $i++) {                     // Déclare variable; Condition; incrémentation
        echo $i;                                       // Execute code
    }

    // Foreach
    $tableau = array(1, 2, 3, 4);                      // Tableau 
    
    foreach ($tableau as &$value) {                    // Parcoure le tableau
        $value = $value * 2;
        return $value;                                 // Retourne le résultat $value
    }
    
    foreach ($tableau as $key => $value) {             // Parcoure le tableau
        echo "{$key} => {$value}";                     // lis la key et la valeur
    }

    // GOTO
    goto nameGoto;                                     // Continue l'exécution script à un autre point du programme. 
    echo 'N affichera pas ce message';
    nameGoto:                                          // Reprend le code à ce niveau
    echo 'Affichera ce message';
    ?>
-->


<!-- Route en PHP
    -- HTACCES 

    RewriteEngine on

    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^(.*)$ index.php?url=$1 [QSA,L]

    -- HTACCES 
    <?php  
    
    
    ?>

 -->

 ```
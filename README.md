# PromileLirwa
Prestashop: <br/>
url: 		http://localhost:8080/procenty  <br/>
login:		admin@admin.com  <br/>
password: 	prestashopadmin  <br/>
 <br/> <br/>
MySQL <br/>
user: 		root <br/>
password: 	prestapassword <br/>
address:	172.17.0.2 <br/>
 <br/> <br/>
obraz sklepu:	procentylirwa/prestashop:v1 <br/>
 <br/> <br/>
====================================================== <br/>
Tworzenie backupu bazy: <br/>
docker exec mysqltest /usr/bin/mysqldump -u root --password=prestapassword DATABASE > backup.sql <br/>
 <br/>
 <br/>
Żeby postawić od nowa na czystej maszynie: <br/>
 <br/>
docker run --detach --name=mysqltest --env="MYSQL_ROOT_PASSWORD=prestapassword" mysql <br/>
get-content C:\Loc\backup.sql | docker exec -i mysqltest /usr/bin/mysql -u root --password=prestapassword mysql <br/>
docker run -ti --name=my-presta -p 8080:80 -d procentylirwa/prestashop:v1 <br/>


# Parser
Wymagania:<br/>
-połączenie z internetem, ponieważ wymagane jest pobranie jQuery <br/>
-niektóre przeglądarki blokują pobieranie całych stron metodą $.get jeżeli skrypt jest zawarty w pliku lokalnym <br/>
(żeby działało w Google Chrome, należy uruchomić przeglądarkę z parametrem '--disable-web-security --user-data-dir') 

Jak używać:<br/>
-wpisać link z listą produktów ze strony http://www.alkoholeswiata.com/ w pole LINK (domyślnie wpisany link z kategorią Piwa) <br/>
-wpisać nazwę kategorii jaką mają mieć pobrane z linku produkty (domyślnie Piwa) <br/>
-nacisnąć przycisk START i poczekać aż pobiorą się wszystkie produkty <br/>
-nacisnąć przycisk CSV i pobrać plik z linku który się pojawił

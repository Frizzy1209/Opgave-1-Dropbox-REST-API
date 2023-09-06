Opgave 1 - Done

Har nu oprettet forbindelse til min Dropbox API
https://www.dropbox.com/home/Apps/Opgave%201%20-%20REST%20API?di=left_nav_browse

Jeg har brugt HTTP-verd - POST

------

Opgave 2 - Done

Brugte https://www.dropbox.com/developers/documentation/http/documentation til at finde det endpoint jeg skal bruge for at lave en ny mappe

Den ser sådan her ud: 
{
    "autorename": false,
    "path": "/TestMappe"
}

https://www.dropbox.com/home/Apps/Opgave%201%20-%20REST%20API/TestMappe?di=left_nav_browse

Jeg har brugt HTTP-verd - POST

------

Opgave 3 - Done

Tjekkede https://www.dropbox.com/developers/documentation/http/documentation for at finde ud af hvilet endpoint jeg skulle bruge for at finde detaljer for en specifik mappe

Den ser sådan her ud: 

{
    "include_deleted": false,
    "include_has_explicit_shared_members": false,
    "include_media_info": false,
    "path": "/TestMappe"
}

og jeg fik så det her output 

{
    ".tag": "folder",
    "name": "TestMappe",
    "path_lower": "/testmappe",
    "path_display": "/TestMappe",
    "id": "id:3-Fm7SrdQxEAAAAAAAAACg"
}

Jeg har brugt HTTP-verd - POST

------

Opgave 4 - Done

Tjekkede https://www.dropbox.com/developers/documentation/http/documentation og fandt det endpoint jeg skulle bruge for at uploade en fil

Det ser sådan her ud: 

{
    "autorename": false,
    "mode": "add",
    "mute": false,
    "path": "/TestMappe/NewDocu.txt",
    "strict_conflict": false
}

Her er det vigtigt at man også ændre sin Header Content-Type til application/octet-stream 

og tilføjer en Header Dropbox-API-Arg, hvor man sætter følgende ind:
 { "autorename": false, "mode": "add", "mute": false, "path": "/TestMappe/NewDocu.txt", "strict_conflict": false }

 Under "path" vælger man først den mappe man vil bruge og så skriver man det navn som det nye document skal hedde.

 Jeg har brugt HTTP-verd - POST

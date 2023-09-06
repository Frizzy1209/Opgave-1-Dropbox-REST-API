Opgave 1 - Done

Har nu oprettet forbindelse til min Dropbox API
https://www.dropbox.com/home/Apps/Opgave%201%20-%20REST%20API?di=left_nav_browse

Jeg har brugt HTTP-verd - POST

------

Opgave 2 - Done

Jeg har brugt HTTP-verd - POST

Brugte https://www.dropbox.com/developers/documentation/http/documentation til at finde det endpoint jeg skal bruge for at lave en ny mappe

Den ser sådan her ud: 

https://api.dropboxapi.com/2/files/create_folder_v2

i body skrev jeg:

{
    "autorename": false,
    "path": "/TestMappe"
}

https://www.dropbox.com/home/Apps/Opgave%201%20-%20REST%20API/TestMappe?di=left_nav_browse

------

Opgave 3 - Done

Jeg har brugt HTTP-verd - POST

Tjekkede https://www.dropbox.com/developers/documentation/http/documentation for at finde ud af hvilet endpoint jeg skulle bruge for at finde detaljer for en specifik mappe

Den ser sådan her ud: 

https://api.dropboxapi.com/2/files/get_metadata

I body skrev jeg:

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

------

Opgave 4 - Done

Jeg har brugt HTTP-verd - POST

Tjekkede https://www.dropbox.com/developers/documentation/http/documentation og fandt det endpoint jeg skulle bruge for at uploade en fil

Det ser sådan her ud: 

https://content.dropboxapi.com/2/files/upload

Det jeg skrev i body:

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

 ------

 Opgave 5 - Done
 
 Jeg har brugt HTTP-verd - POST

 Tjekkede https://www.dropbox.com/developers/documentation/http/documentation og fandt det endpoint jeg skulle bruge for at slette en fil

 Det ser sådan her ud:

 https://api.dropboxapi.com/2/files/delete_v2

 og i body skrev jeg det her:

 {
    "path": "/TestMappe/NewDocu.txt"
}

------

Opgave 6 - Done

Jeg har brugt HTTP-verd - POST

Tjekkede https://www.dropbox.com/developers/documentation/http/documentation og fandt det endpoint jeg skulle bruge for at søge efter en fil

Det ser sådan her ud:

https://api.dropboxapi.com/2/files/search_v2

og i body skrev jeg:

{
    "match_field_options": {
        "include_highlights": false
    },
    "options": {
        "file_status": "active",
        "filename_only": false,
        "max_results": 20,
        "path": "/TestMappe"
    },
    "query": "test"
}

Her skriver man i path hvilken mappe man vil søge i og ud fra query skriver man det man vil søge efter 

------



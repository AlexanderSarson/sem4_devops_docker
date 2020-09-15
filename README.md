# Opsætning af containers
1. Under containeren traefik i labels /docker/docker-compose-yml ændre mailen adressen EXAMPLE@EXAMPLE.com til en anden ellers vil automatisk tls certificate ikke virke
2. Der er en eksempel på i docker-compose.yml filen, hvordan et load balancing scenarie med automatisk opsætning af reverse proxy og tls certificate vil se ud.
Man kan fjerne scale: 2 fra container, hvis man ikke vil load balance.
BEMÆRK at scale: kun virker i docker-compose v2.2, så hvis man vil bruge en nyere version skal denne fjernes fra filen.
3. for at lave en ny container skal man blot kopiere eksemplet fra docker-compose filen og ændre domainet, samt hvor der står CHANGEME.
4. Jeg anbefaler at for hver ny service/container man vil have kørende at man laver en compose fil, kopiere den op på dropletten under sin egen folder, hvorefter der skal køres docker-compose up -d.
Traefik finder selv ud af at opdage containeren, trække et certificat og dirigere trafikken hen til containeren med de informationer man har sat på labels.
BEMÆRK at det er vigtigt at man i sin dockerfil bruger EXPOSE ellers ved traefik ikke hvilken port den skal sende trafikken hen til.
Man kan også bruge ports under container i docker-compose, hvis man har glemt EXPOSE i dockerfile

# Opsætning af droplet
1. Opret en konto hos digitalocean.com og log in
2. Tryk på Droplets i fanen i venstre side
3. Tryk på Create Droplet
4. Tryk på fanen Marketplace
5. Søg efter og vælg Docker
6. Tjek at Basic plan er valgt
7. Vælg den mindste droplet - 5$/mo
8. Vælg Frankfurt datacenter
9. Tryk på New SSH Key
10. Kopier public key info ind
11. Tryk Add SSH Key
12. Tjek at den nye SSH Key er valgt
13. lad resten af indstillingerne være standard og scroll ned til bunden og tryk Create Droplet

# Opsætning af domain


# Opsætning af docker
1. Clone dette repo
2. Log in på droplet via ssh
3. Kør kommando'en "docker network create dev"
4. Opret en mappe som hedder docker under /home
5. Opret en mappe som hedder config under /home/docker
6. kopier docker-compose filen fra Traefik op på dropletten i /home/docker/config mappen
7. kør kommando'en "docker-compose up -d" fra mappen /home/docker/config

# Opsætning af ny container
1. brug Example_container_traefik docker-compose filen til at lave en ny docker-compose fil - husk at lave de nødvendige ændringer i labels, hvor der står "CHANGEME", samt domain
2. Opret en mappe under /home/docker med et sigende navn
3. Kopier docker-compose filen op på dropletten i den nye mappe
4. Kør kommando'en "docker-compose up -d"




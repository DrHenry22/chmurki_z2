# Projekt 2
## Link do repozytorium
[https://github.com/DrHenry22/chmurki_z2](https://github.com/DrHenry22/chmurki_z2])
[https://hub.docker.com/repository/docker/drhenry22/chmurki2/](https://hub.docker.com/repository/docker/drhenry22/chmurki2/)
### Zadanie 1
[Link do zadania Github Actions](hhttps://github.com/DrHenry22/chmurki_z2/actions/runs/1732853217)
Do wykonania zadania 1 wykorzystano plik Dockerfile, przy pomocy którego budowana jest aplikacja webowa. W celu uruchomienia zadania poprzez Github Actions stworzono workflow, w którym użyto pliku [main.yml](https://github.com/DrHenry22/chmurki_z2/blob/master/.github/workflows/main.yml).
### Zadanie 2
[Link do zadania Github Actions](https://github.com/DrHenry22/chmurki_z2/actions/runs/1732883250)
W celu zbudowania obrazów multi-platformowych dodano do pliku [main2.yml](hhttps://github.com/DrHenry22/chmurki_z2/blob/master/.github/workflows/main2.yml) sekcję, w której zadeklarowano wykorzystanie platformy QEMU:
```
- name: Set up QEMU
  uses: docker/setup-qemu-action@master
  with:
  platforms: all
```
jak również zadeklarowano docelowe platformy w sekcji Build and Push:
`platforms: linux/amd64, linux/arm64/v8, linux/arm/v7`
### Zadanie 3
[Link do zadania Github Actions](https://github.com/DrHenry22/chmurki_z2/actions/runs/1732940754)
Do wykonania zadania 3 wykorzystano plik Dockerfile.v2, w którym zadeklarowano wieloetapowe tworzenie obrazów. Dzięki uprzedniemu wykorzystaniu silnika BuildKit, nie jest konieczna żadna zmiana w pliku yml ([main3.yml](https://github.com/DrHenry22/chmurki_z2/blob/master/.github/workflows/main3.yml)).
### Zadanie 4
Do wykonania zadania 4 wykorzystano wbudowaną w build-push-action funkcję cache. W sekcji Build and Push zadeklarowano lokalizację przechowywania cachu:
```
cache-from: type=registry,ref=drhenry22/chmurki2:image4-cache
cache-to: type=registry,ref=drhenry22/chmurki2:image4-cache,mode=max
```
Dzięki wykorzystaniu mechanizmu cachowania czas tworzenia obrazu skrócił się o ponad połowę.

[Zadanie GA - ponowne uruchomienie z wykorzystaniem cache](https://github.com/DrHenry22/chmurki_z2/actions/runs/1733102436)

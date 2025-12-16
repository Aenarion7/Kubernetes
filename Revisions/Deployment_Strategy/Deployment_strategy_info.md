## 1) Zero spadku dostępności (polecane, jeśli masz zapas zasobów)

        maxUnavailable: 0, maxSurge: 1

        maks. Podów naraz: 3 + 1 = 4

        min. dostępnych: 3 - 0 = 3

w praktyce: 3 stare + 1 nowy, potem 2 stare + 1 nowy (bo jeden stary schodzi), itd.

        strategy:
        type: RollingUpdate
        rollingUpdate:
            maxSurge: 1
            maxUnavailable: 0

## 2) Bez “nadmiaru” (gdy nie możesz mieć 4 Podów naraz)

maxUnavailable: 1, maxSurge: 0

maks. Podów naraz: 3 + 0 = 3

min. dostępnych: 3 - 1 = 2

w praktyce: najpierw schodzi 1 stary → masz 2 dostępne, potem wchodzi 1 nowy → znów 3, itd.

    strategy:
    type: RollingUpdate
    rollingUpdate:
        maxSurge: 0
        maxUnavailable: 1

## 3) Szybciej, ale nadal bez spadku dostępności (większy “surge”)

maxUnavailable: 0, maxSurge: 2

maks. Podów naraz: 3 + 2 = 5

min. dostępnych: 3

w praktyce: możesz szybciej “wpompować” nową wersję (np. od razu 2 nowe obok 3 starych), potem zbijasz stare.

    strategy:
    type: RollingUpdate
    rollingUpdate:
        maxSurge: 2
        maxUnavailable: 0

## 4) Najprościej: nigdy dwie wersje naraz (zwykle downtime)

Recreate

najpierw 0 starej, potem rośnie nowa do 3

prawie na pewno przerwa w dostępności

    strategy:
    type: Recreate

Ważna uwaga praktyczna

“Dostępność” w sensie maxUnavailable ma sens dopiero, gdy masz dobrze ustawione readinessProbe (i ewentualnie minReadySeconds). Bez tego Pod może być liczony jako “gotowy” za wcześnie.
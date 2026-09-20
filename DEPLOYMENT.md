# Etap 2 — wspólna baza online (bezpłatny start)

Ta wersja zachowuje wygląd Prototypu 2, ale zamiast localStorage korzysta ze wspólnej bazy Supabase. Dzięki temu nauczyciel i uczniowie mogą pracować na tych samych danych.

## 1. Utwórz darmowy projekt Supabase
1. Wejdź na https://supabase.com/
2. Załóż konto i wybierz **New project**.
3. Zapisz hasło projektu.
4. Po utworzeniu projektu otwórz **SQL Editor**.
5. Wklej CAŁĄ zawartość pliku `supabase_schema.sql` i wybierz **Run**.

## 2. Włącz logowanie anonimowe dla uczniów
W Supabase: **Authentication → Providers → Anonymous Sign-Ins** i włącz tę opcję.

## 3. Utwórz konto nauczyciela
W Supabase: **Authentication → Users → Add user**.
Podaj swój adres e-mail i hasło.

Następnie skopiuj UUID tego użytkownika i w SQL Editor uruchom:

insert into public.teachers (user_id) values ('TU_WKLEJ_UUID_NAUCZYCIELA');

## 4. Pobierz dane API
W Supabase: **Project Settings → API**.
Skopiuj:
- Project URL
- Publishable/anon key

W pliku `config.js` wpisz je zamiast dwóch wartości `PASTE_...`.

## 5. Test lokalny
Najprościej możesz otworzyć stronę przez prosty serwer lokalny. Jeśli nie masz narzędzi programistycznych, możesz od razu wrzucić pliki na GitHub i uruchomić GitHub Pages.

## 6. Darmowy hosting
Możesz użyć GitHub Pages albo Vercel Hobby. Vercel ma obecnie plan Hobby za $0/mies., a Supabase Free obejmuje m.in. 500 MB bazy na projekt. Limity mogą się zmieniać — sprawdź aktualny panel przed uruchomieniem większej liczby grup.

## Ważne
- Nie umieszczaj w `config.js` klucza service_role. Używamy tylko klucza publicznego/publishable/anon.
- Dane są wspólne dla urządzeń po podłączeniu do tego samego projektu Supabase.
- To jest pierwsza wersja Etapu 2. Nadal warto później dodać: zarządzanie uczniami, edycję/usuwanie rekordów, bardziej rozbudowane typy pytań, filtrowanie, eksport wyników i dokładniejsze zabezpieczenia.


### Domyślne grupy demonstracyjne
- B2.2 — kod pokoju B2G101
- B2.4 — kod pokoju C1A202

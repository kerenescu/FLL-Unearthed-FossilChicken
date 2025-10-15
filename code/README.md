# 🤖 Cod pentru robot LEGO SPIKE Prime

##  CONFIGURARE DE BAZĂ
──────────────────────────────
1. **Motoarele principale de deplasare** sunt conectate la porturile **E** și **F**.  
   ```python
   motor_pair.unpair(motor_pair.PAIR_1)  # deconectează perechile implicite
   motor_pair.pair(motor_pair.PAIR_1, port.E, port.F)  # definește o pereche de motoare pentru deplasare
   ```

2. **Constantele de calibrare:**
   - `wheel_circumference` → circumferința roții (pentru a converti cm în grade de rotație)
   - `gyro_multiplier` → factor de conversie pentru rotații precise
   - `speed_correction` → corecție pentru diferențele între roți

---

##  FUNCȚII DE MIȘCARE
──────────────────────────────
- `move(distance_cm, speed)` → deplasează robotul înainte o distanță în cm  
- `move_tank()` → permite viteze diferite pentru fiecare roată (pentru curbe)  
- `move_backward()` → deplasează robotul înapoi  
- `move_for_time()` → deplasează robotul o durată fixă de timp  

---

##  FUNCȚII DE ROTAȚIE
──────────────────────────────
- `turn(angle)` → rotește robotul cu unghiul dat, folosind giroscopul  
- `turn_left()` / `turn_right()` → rotații predefinite de 90° stânga/dreapta  
- `curve()` → mișcare în curbă cu un anumit nivel de virare (steering)  

---

##  FUNCȚII PENTRU MOTOARE INDIVIDUALE
──────────────────────────────
- `run_motor()` → rulează un motor individual pe un anumit port și un număr de grade  
- `grab()` și `release()` → simulează prinderea și eliberarea unui obiect (cu un atașament)  
- `lift_up()` și `lift_down()` → ridică sau coboară un atașament montat pe robot  

---

##  FUNCȚII DE SINCRONIZARE
──────────────────────────────
- `wait()` și `wait_ms()` → fac robotul să aștepte un timp specificat  

---

##  FUNCȚII DE FEEDBACK VIZUAL
──────────────────────────────
- `show_display()` → afișează text pe matricea LED a hubului  
- `show_number()` → afișează un număr pe display  

---

## FUNCȚII DE RESETARE
──────────────────────────────
- `reset_yaw()` → resetează orientarea giroscopului  
- `reset_motors()` → resetează poziția motoarelor principale  

---

##  FUNCȚII COMPUSE
──────────────────────────────
- `square()` → mișcă robotul în forma unui pătrat (4 laturi și rotații de 90°)  
- `approach_and_grab()` → robotul merge înainte, apucă un obiect și revine la bază  
- `push_and_return()` → împinge un obiect și revine  
- `turn_and_align()` → se rotește și merge până la un perete  

---

##  FUNCȚIE DE TESTARE
──────────────────────────────
- `test_all_functions()` → testează toate funcțiile principale – mișcări, rotații, pătrat etc.  

---

##  EXEMPLU DE MISIUNE
──────────────────────────────
- `mission_1()` → exemplu de acțiune complexă ce combină mai multe funcții (mers, rotire, grab etc.)  
  > Este comentată parțial pentru testare manuală.

---

##  PROGRAM PRINCIPAL
──────────────────────────────
- `main()` → resetează yaw-ul și motoarele, apoi rulează testele (sau misiunea 1)  
- `runloop.run(main())` → pornește execuția asincronă a întregului program  

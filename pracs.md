## Prolog programs
### 6. Expert System for Medical Diagnosis

```prolog
% Define symptoms for diseases
symptom(flu, fever).
symptom(flu, cough).
symptom(flu, shortness_of_breath).
symptom(migraine, headache).
symptom(migraine, nausea).
symptom(migraine, vomiting).

% Predict disease based on symptoms
diagnose(Disease) :-
    findall(Symptom, symptom(Disease, Symptom), Symptoms),
    write('Symptoms of '), write(Disease), write(': '), write(Symptoms), nl.

% Display symptoms based on disease
predict(Symptoms, Disease) :-
    findall(D, (member(S, Symptoms), symptom(D, S)), Diseases),
    sort(Diseases, UniqueDiseases),
    write('Possible diseases: '), write(UniqueDiseases), nl.
```

**Example Queries and Outputs:**

- Predict disease based on symptoms:
  ```prolog
  ?- predict([fever, cough, shortness_of_breath], Disease).
  Possible diseases: [flu]
  ```

- Display symptoms based on disease:
  ```prolog
  ?- diagnose(flu).
  Symptoms of flu: [fever, cough, shortness_of_breath]
  ```

### 7. Prolog Program to Append Two Lists

```prolog
append([], L, L).
append([H|T], L, [H|R]) :- append(T, L, R).
```

**Example Query and Output:**

```prolog
?- append([1, 2], [3, 4], Result).
Result = [1, 2, 3, 4].
```

### 8. Prolog Program to Reverse a List

```prolog
reverse([], []).
reverse([H|T], R) :- reverse(T, RevT), append(RevT, [H], R).
```

**Example Query and Output:**

```prolog
?- reverse([1, 2, 3, 4], Result).
Result = [4, 3, 2, 1].
```

### 9. Prolog Program to Find the Nth Element from a List of Integers

```prolog
nth_element(1, [H|_], H).
nth_element(N, [_|T], Elem) :- N > 1, N1 is N - 1, nth_element(N1, T, Elem).
```

**Example Query and Output:**

```prolog
?- nth_element(3, [10, 20, 30, 40, 50], Element).
Element = 30.
```

### 10. Prolog Program to Check Whether a Given Element is a Member of a List

```prolog
member(X, [X|_]).
member(X, [_|T]) :- member(X, T).
```

**Example Query and Output:**

```prolog
?- member(3, [1, 2, 3, 4, 5]).
true.
```

These Prolog programs can be run in any Prolog interpreter, such as SWI-Prolog. The example queries demonstrate how to use each program and the expected outputs.

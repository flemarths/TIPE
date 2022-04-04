## Sujet Centrale IPT

### Géométrie 

#### Q1: *Écire la fonction d'entête* 

```
def vect(A,B):
	res=np.array(3)
    for i in range [0,3]:
	    res[i]=B[i]-A[i]
    return res
```  
  
ou encore  
  
```
def vect(A,B):  
    return B-A
```

#### Q2: *Écrire une fonction d'entête*

```
def ps(v1,v2):
    return np.inner(v1,v2)
```

#### Q3: *Écrire une fonction d'entête*

```
def norme(v):
	return np.sqrt(ps(v,v))
```

#### Q4: *Écrire une fonction d'entête*

```
def unitaire(v):
	return (1/norme(v))*v
```

#### Q5: Que font les fonctions **pt**, **dir** et **ra** ci-dessous ?

  * La fonction *pt* retourne le point du rayon (S,u) de mesure algébrique *t* 
  devant être positive ou nulle.  
  
  * La fonction *dir* retourne le vecteur unitaire support du vecteur AB,
  et donc le vecteur directeur de la droite (AB).  
  
  * La fonction *ra* retourne le rayon d'origine A et de vecteur unitaire le
  vecteur directeur de (AB) : elle retourne donc le rayon d'origine *A* et 
  passant par *B*
  

#### Q6: *Écrire une fonction d'entête*

```
def sp(A,b):
	return (A, norme(vec(A,B)))
```

#### Q8: *Écrire une fonction d'entête*

 ```
def intersection(r,s):
	(C,rc) = s #sphère de centre C et de rayon rc
	(A, u) = r #rayon d'origine A et de vecteur directeur u
	a = 1
	b = 2*ps(u, vec(C,A))
	c = ps(vec(C,A),vec(C,A))-rc**2
	delta = b**2-4*a*c #Calcul du discriminant
	if delta < 0:
		return None
	else:
		#premier point est celui de distance minimale
		#soit donc pour la solution avec -racine de delta
		t = (-b-np.sqrt(delta))/(2*a)
		#Résultat valide seulement pour t>0
		if t > 0:
			return (pt(r,t),t)
		else:
			return None
```

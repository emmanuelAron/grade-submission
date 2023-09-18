# grade-submission

Ceci est un push du projet issu du cours: (chapitre : Grade submission - ou validation du formulaire)<br />
https://www.udemy.com/course/the-complete-spring-boot-development-bootcamp<br />

Objet Grade :<br />
propriétés : String name ; String subject;String score; (Exemple : Potter ; Potions ; C+)

2 formulaires:
Le formulaire form.html et grades.html

Le formulaire grades.html est visible sur l'URL http://localhost:8081/grades car on a @GetMapping("/grades") 
-> Dans le GradeController : 
- Une liste d'objets Grade studentGrades est passé en attribut au Modele.<br /> 
- Cette liste d'objets correspond aux lignes du formulaire ajoutées dynamiquement<br />
Le formulaire form.html est visible sur l'URL http://localhost:8081 car on a @GetMapping("/")<br />
-> Dans le GradeController :<br />
  Un objet Grade est passé en attribut au Modele.<br />
  -> Correspond aux 3 champs du formulaire (Name, Score,Subject).<br />
  -> Un champ par propriété de l'objet Grade.



Controller GradeController.java:
                                                     
On a également une méthode: 
 @PostMapping("/handleSubmit")
    public String submitForm(Grade grade){
      studentGrades.add(grade);
      return "redirect:/grades";
    }
    qui correspond à l'action handleSubmit dans le formulaire "post".Lorsqu'on valide le formulaire (methode POST) on est redirigé ("redirect:/grades") vers l'URL : http://localhost:8081/grades
    
                                                                                                         

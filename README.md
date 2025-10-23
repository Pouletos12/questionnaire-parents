<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Questionnaire pour Parents d'Élèves de 2 Ans</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; padding: 20px; background-color: #f9f9f9; }
        h1 { text-align: center; color: #333; }
        form { background: white; padding: 20px; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        label { display: block; margin: 10px 0 5px; font-weight: bold; }
        input[type="radio"] { margin-right: 10px; }
        button { background: #4CAF50; color: white; padding: 10px 20px; border: none; border-radius: 4px; cursor: pointer; width: 100%; }
        button:hover { background: #45a049; }
        #message { text-align: center; margin-top: 20px; color: green; }
    </style>
</head>
<body>
    <h1>Questionnaire pour Parents d'Élèves de 2 Ans</h1>
    <p>Répondez à ces questions tests QCM. Vos réponses seront collectées anonymement.</p>
    
    <form id="questionnaireForm">
        <label>Q1 : QUI</label>
        <input type="radio" name="Q1_QUI" value="Option A" required> Option A<br>
        <input type="radio" name="Q1_QUI" value="Option B"> Option B<br>
        <input type="radio" name="Q1_QUI" value="Option C"> Option C<br>
        
        <label>Q2 : Quoi</label>
        <input type="radio" name="Q2_Quoi" value="Choix 1" required> Choix 1<br>
        <input type="radio" name="Q2_Quoi" value="Choix 2"> Choix 2<br>
        <input type="radio" name="Q2_Quoi" value="Choix 3"> Choix 3<br>
        
        <label>Q3 : Donc</label>
        <input type="radio" name="Q3_Donc" value="Réponse X" required> Réponse X<br>
        <input type="radio" name="Q3_Donc" value="Réponse Y"> Réponse Y<br>
        <input type="radio" name="Q3_Donc" value="Réponse Z"> Réponse Z<br>
        
        <button type="submit">Envoyer</button>
    </form>
    
    <div id="message"></div>
    
    <script>
        const form = document.getElementById('questionnaireForm');
        const scriptURL = 'https://script.google.com/macros/s/AKfycbx62sJiwPeI0EuAO3R89XV6A3NcU0gxfR8RdyjfOc257jR56U4gYaPn8TbUhTgMh_ceMA/exec'; // Remplacez par l'URL de votre Apps Script (ex. https://script.google.com/macros/s/AKfycbw.../exec)
        
        form.addEventListener('submit', e => {
            e.preventDefault();
            const formData = new FormData(form);
            fetch(scriptURL, { method: 'POST', body: formData })
                .then(response => {
                    document.getElementById('message').innerText = 'Merci ! Vos réponses ont été envoyées.';
                    form.reset();
                })
                .catch(error => console.error('Erreur:', error));
        });
    </script>
</body>
</html>

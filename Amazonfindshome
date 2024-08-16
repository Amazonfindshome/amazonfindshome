<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Links Invoegen en Verwijderen</title>
    <style>
        /* Voeg wat eenvoudige stijlen toe voor betere leesbaarheid */
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            margin: 10px 0;
        }
        .remove-btn {
            margin-left: 10px;
            color: red;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Voeg je links toe en verwijder ze</h1>
    <ul id="link-list"></ul>

    <input type="text" id="link-input" placeholder="Voer je link in">
    <input type="text" id="name-input" placeholder="Voer de naam van de link in">
    <button onclick="addLink()">Link toevoegen</button>

    <script>
        function addLink() {
            const linkInput = document.getElementById('link-input');
            const nameInput = document.getElementById('name-input');
            const linkList = document.getElementById('link-list');

            // Controleer of beide velden zijn ingevuld
            if (linkInput.value && nameInput.value) {
                const listItem = document.createElement('li');
                const link = document.createElement('a');
                link.href = linkInput.value;
                link.textContent = nameInput.value;
                link.target = "_blank"; // Opent de link in een nieuw tabblad

                // Maak een verwijderknop
                const removeBtn = document.createElement('span');
                removeBtn.textContent = 'Verwijderen';
                removeBtn.className = 'remove-btn';
                removeBtn.onclick = function() {
                    linkList.removeChild(listItem);
                };

                listItem.appendChild(link);
                listItem.appendChild(removeBtn);
                linkList.appendChild(listItem);

                // Maak de invoervelden leeg na het toevoegen
                linkInput.value = '';  
                nameInput.value = '';  
            } else {
                alert("Zorg ervoor dat beide velden zijn ingevuld.");
            }
        }
    </script>
</body>
</html>

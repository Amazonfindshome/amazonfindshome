<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Add and Remove Links</title>
    <style>
        /* Add some simple styles for better readability */
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
    <h1>Add and Remove Links</h1>
    <ul id="link-list"></ul>

    <input type="text" id="link-input" placeholder="Enter your link">
    <input type="text" id="name-input" placeholder="Enter the link name">
    <button onclick="addLink()">Add Link</button>

    <script>
        function addLink() {
            const linkInput = document.getElementById('link-input');
            const nameInput = document.getElementById('name-input');
            const linkList = document.getElementById('link-list');

            // Check if both fields are filled
            if (linkInput.value && nameInput.value) {
                const listItem = document.createElement('li');
                const link = document.createElement('a');
                link.href = linkInput.value;
                link.textContent = nameInput.value;
                link.target = "_blank"; // Opens the link in a new tab

                // Create a remove button
                const removeBtn = document.createElement('span');
                removeBtn.textContent = 'Remove';
                removeBtn.className = 'remove-btn';
                removeBtn.onclick = function() {
                    linkList.removeChild(listItem);
                };

                listItem.appendChild(link);
                listItem.appendChild(removeBtn);
                linkList.appendChild(listItem);

                // Clear the input fields after adding
                linkInput.value = '';  
                nameInput.value = '';  
            } else {
                alert("Please make sure both fields are filled.");
            }
        }
    </script>
</body>
</html>

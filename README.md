# -API-Checkpoint

Voici comment vous pouvez créer une application React qui consomme l'API JSONPlaceholder pour afficher une liste d'utilisateurs :

Créer un projet :

bash
Copier le code
npx create-react-app user-list
cd user-list
Installer Axios :

bash
Copier le code
npm install axios
Créer le fichier UserList.js dans le dossier src.

Dans UserList.js, utilisez le code suivant :

javascript
Copier le code
import React, { useEffect, useState } from 'react';
import axios from 'axios';

const UserList = () => {
  const [listOfUsers, setListOfUsers] = useState([]);

  useEffect(() => {
    const fetchUsers = async () => {
      const response = await axios.get('https://jsonplaceholder.typicode.com/users');
      setListOfUsers(response.data);
    };
    fetchUsers();
  }, []);

  return (
    <div>
      <h1>Liste des Utilisateurs</h1>
      <ul>
        {listOfUsers.map(user => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
};

export default UserList;
Inclure UserList dans votre composant principal (par exemple, App.js).

Démarrer votre application :

bash
Copier le code
npm start
Cela vous permettra d'afficher la liste des utilisateurs à partir de l'API JSONPlaceholder. Vous pouvez également styliser votre application selon vos préférences !

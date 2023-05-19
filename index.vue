<!DOCTYPE html>
<html>


<head>
<meta charset="UTF-8">
    <title>Minha Página Vue</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #575b57;
        }

        h1 {
    color: white;
    font-family: "Arial", sans-serif;
    font-size: 24px;
    font-weight: bold;
}

li {
    color: white;
    font-family: "Arial", sans-serif;
    font-size: 16px;
    font-weight: normal;
}

    </style>
</head>

<body>
    <div id="app">
        <h1>{{ mensagem }}</h1>
        <input style='border-radius: 20px;' type="text" v-model="mensagem">
        <button @click="adicionarItem">Adicionar Item</button>
        <ul>
            <li v-for="item in itens" :key="item.id">{{ item.nome }}</li>
        </ul>
    </div>

    <script>
        const app = new Vue({
            el: '#app',
            data: {
                mensagem: 'Olá teste!',
                itens: [
                    { id: 1, nome: 'Item 1' },
                    { id: 2, nome: 'Item 2' },
                    { id: 3, nome: 'Item 3' }
                ]
            },
            methods: {
                adicionarItem() {
                    const novoItem = {
                        id: this.itens.length + 1,
                        nome: 'Novo Item ' + (this.itens.length + 1)
                    };
                    this.itens.push(novoItem);
                }
            }
        });
    </script>
</body>

</html>

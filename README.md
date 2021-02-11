# Blog

App construida en React, haciendo uso de Redux y Redux-Thunk para el manejo del state de la app.

Hecha en base a las unidades 18 y 19 ('Async Actions with Redux Thunk' y 'Redux Store Design') del curso Modern React with Redux de Stephen Grider en Udemy.

La app consiste en un "blog" que muestra 100 post creados por 10 usuarios ficticios. Todo el contenido de los posts, incluidos los nombres de los usuarios es provisto por [JSONPlaceholder](https://jsonplaceholder.typicode.com).

A la hora de crear nuestro store, se usa Redux Thunk como middleware para poder trabajar con aquellas actions despachadas por nuestros action creators cuyo payload **no** sea un objeto. En este caso, se usa en todos nuestros action creators pues son ellos quienes realizan los pedidos correspondientes a JSONPlaceholder para poder recibir los posts y nombres que son el contenido de nuestra app.

Se hace uso de un action creator (fetchPostsAndUsers) que invoca a otros dos (fetchPosts y fetchUser). Son estos últimos quienes realizan el pedido a la API de JSONPlaceholder, el action creator que los invoca permite hacer uso de lodash para poder limitar los pedidos hechos a la API, volviendo la app más eficiente. De realizar más de 100 pedidos (o requests) a la API, una por cada post, la API ahora realiza 1 por cada usuario, y ha cada usuario le corresponde la autoría de 10 posts.

Link a app hosteada en Netlify: [Link](https://galedesma-blog.netlify.app)

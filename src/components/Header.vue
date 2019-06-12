<template>
    <v-content>
       <div>
           <ul>
                
                <li><Router-link to="/home">Home</Router-link></li>
                <li><Router-link to="/news">News</Router-link></li>
                <li><Router-link to="/contact">Contact</Router-link></li>
                <li><Router-link to="/about">About</Router-link></li>
            </ul>
           
       </div>
    </v-content>
</template>

<style lang="scss">
        ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #333;
        }

        li {
            float: right;
        }

        li a {
            display: block;
            color: white;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }

        /* Change the link color to #111 (black) on hover */
        li a:hover {
            background-color: #111;
        }
</style>

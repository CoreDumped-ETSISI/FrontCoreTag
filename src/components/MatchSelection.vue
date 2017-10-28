<template>
    <div class="collection">
<!--Change this for a query with all the matches available-->
        <a href="#!" class="collection-item">Alvin</a>
        <a href="#!" class="collection-item active">Alvin</a>
        <a href="#!" class="collection-item">Alvin</a>
        <a href="#!" class="collection-item">Alvin</a>
    </div>
</template>

<script>
export default {
    name: "MatchSelection",
    data:{
        
    },
    methods:{
        loadData(){
            $.get("http://192.168.0.25:3000/api/getMatches", //Required URL of the page on server
                function(data,status,request){
                    console.log("Matches requested!");

                }
            );
        }
    }
}

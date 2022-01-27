<script>

</script>

<div class="card container">
    <div class="card-content">
    <slot></slot>
    </div>
</div>

<style>
    .card{
        
        background-color: white;
        padding: 10px 15px;
        border-radius: 10px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        margin-right: 100px;
        height: 400px;
        width: 450px;
        text-align: center;
        display: grid;
        grid-template-columns: 300px;
        grid-template-rows: 210px;
        grid-template-areas: "image" "text" "stats";
        margin: 20px;
        font-family: 'Poppins';
        border-radius: 18px;
        background: #06D6A0;;
        box-shadow: 5px 5px 15px rgba(0,0,0,0.9);
        transition: 0.5s ease;
        cursor: pointer;


    }   

</style>
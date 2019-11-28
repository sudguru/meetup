<script>
    export let meetup;
</script>
<style>
    .meetup {
        margin-top: 20px;
    }
</style>

    <div class="card meetup" style="width: 100%">
        <img src="{meetup.imageUrl}" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{meetup.title}</h5>
            <small>{meetup.address}</small>
            <p class="card-text">{meetup.subtitle}</p>
            <p class="card-text">{meetup.description}</p>
        </div>
        <div class="card-body">
            <a href="mailto:{meetup.contactEmail}" class="card-link">Contact</a>
            <a href="/" class="card-link">Show Details</a>
            <a href="/" class="card-link">Favorite</a>
        </div>
    </div>


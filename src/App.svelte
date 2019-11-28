<script>
	import Header from './UI/Header.svelte';
	import MeetupItem from './Meetups/MeetupItem.svelte';
	let title = '';
	let subtitle = '';
	let contactEmail = '';
	let imageUrl = '';
	let description = '';
	let address = '';
	let meetups = [
		{
			id: 'm1',
			title: 'Coding BootCamp',
			subtitle: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
			description: 'Hendrerit imperdiet gravida auctor luctus platea mus elit facilisi facilisi fermentum malesuada pulvinar. Sapien nam hymenaeos mauris, elit dictumst elementum vitae libero. Pede neque feugiat donec volutpat venenatis. Taciti per vitae ridiculus.',
			imageUrl: 'https://image.shutterstock.com/image-photo/mountains-during-sunset-beautiful-natural-260nw-407021107.jpg',
			address: '27th North Road, 235432, NY',
			contactEmail: 'code@email.com'
		},
		{
			id: 'm1',
			title: 'Swim Together',
			subtitle: 'Aenean sem consequat eleifend. Facilisis viverra justo hac ipsum purus aptent est condimentum augue orci ad dis auctor scelerisque pede vitae nostra litora sodales. Volutpat accumsan, pulvinar. Congue enim auctor lobortis tempor. Laoreet.',
			description: 'Hendrerit imperdiet gravida auctor luctus platea mus elit facilisi facilisi fermentum malesuada pulvinar. Sapien nam hymenaeos mauris, elit dictumst elementum vitae libero. Pede neque feugiat donec volutpat venenatis. Taciti per vitae ridiculus.',
			imageUrl: 'https://image.shutterstock.com/image-photo/colorful-flower-on-dark-tropical-260nw-721703848.jpg',
			address: '27th South Road, 235432, CA',
			contactEmail: 'sudeep@gmail.com'
		},
		
	];
	
	function addMeetup() {
		const Meetup = {
			id : Math.random().toString(),
			title,
			subtitle,
			address,
			description,
			contactEmail,
			imageUrl
		}
		meetups = [Meetup, ...meetups];
	}
</script>


<Header />
<div class="container">
	<div class="row justify-content-md-center">
		<div class="col-md-6">
			<form class="mt-3" on:submit|preventDefault="{addMeetup}">
				

				<div class="form-group">
					<label for="subtitle">Subtitle</label>
					<input type="text" class="form-control" bind:value={subtitle} id="subtitle">
				</div>

				<div class="form-group">
					<label for="description">Description</label>
					<input type="text" class="form-control" bind:value="{description}" id="description">
				</div>

				<div class="form-group">
					<label for="address">Address</label>
					<input type="text" class="form-control" bind:value="{address}" id="address">
				</div>

				<div class="form-group">
					<label for="imageUrl">Image Url</label>
					<input type="text" class="form-control" bind:value="{imageUrl}" id="imageUrl">
				</div>

				<div class="form-group">
					<label for="contactEmail">Email address</label>
					<input type="email" class="form-control" bind:value="{contactEmail}" id="contactEmail">
				</div>
				<button type="submit" class="btn btn-primary">Save Meetup</button>
			</form>
		</div>
	</div>
	{#each meetups as meetup}
		<div class="row justify-content-md-center">
			<div class="col-md-6">
				<MeetupItem {meetup} />
			</div>
		</div>
	{/each}
</div>

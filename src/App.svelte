<script>
	import Header from './UI/Header.svelte';
	import Item from './Meetups/Item.svelte';
	const meetups = [
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
		
	]
</script>


<Header />

{#each meetups as meetup}
	<Item />
{/each}
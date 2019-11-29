<script>
	import Header from './UI/Header.svelte';
	import MeetupItem from './Meetups/MeetupItem.svelte';
	import TextInput from './UI/TextInput.svelte';

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
	const titleCtrl = {
		label: 'Title',
		type: 'text',
		id: 'title',
		rows: 0,
		helpText: 'Enter title Here',
		required: 'required',
		value: title
	}
	const subtitleCtrl = {
		label: 'Subtitle',
		type: 'text',
		id: 'subtitle',
		rows: 0,
		helpText: 'Enter subtitle Here',
		required: 'required'
	}
	const descriptionCtrl = {
		label: 'Description',
		type: 'textarea',
		id: 'desription',
		rows: 0,
		helpText: 'Enter Description Here',
		required: 'required'
	}

	const addressCtrl = {
		label: 'Address',
		type: 'textarea',
		id: 'desription',
		rows: 0,
		helpText: 'Enter Address Here',
		required: 'required'
	}
	const imageUrlCtrl = {
		label: 'Image Url',
		type: 'text',
		id: 'imageUrl',
		rows: 0,
		helpText: 'Enter Image URL Here',
		required: 'required'
	}

	const contactEmailCtrl = {
		label: 'Contact Email',
		type: 'email',
		id: 'contactEmail',
		rows: 0,
		helpText: 'Enter contact Email Here',
		required: 'required'
	}
</script>


<Header />
<div class="container">
	<div class="row justify-content-md-center">
		<div class="col-md-6">
			<form class="mt-3" on:submit|preventDefault="{addMeetup}">
				
				<TextInput value="{title}" control="{titleCtrl}" on:input={event => title = event.target.value} />
				<TextInput value="{subtitle}" control="{subtitleCtrl}" on:input={event => subtitle = event.target.value} />
				<TextInput value="{description}" control="{descriptionCtrl}" on:input={event => description = event.target.value} />
				<TextInput value="{address}" control="{addressCtrl}" on:input={event => address = event.target.value} />
				<TextInput value="{imageUrl}" control="{imageUrlCtrl}" on:input={event => imageUrl = event.target.value} />
				<TextInput value="{contactEmail}" control="{contactEmailCtrl}" on:input={event => contactEmail = event.target.value} />
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

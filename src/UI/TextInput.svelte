<script>
	export let control;
</script>
<div class="form-group">
	<label for="title">{control.label}</label>
	{#if control.type === 'textarea'}
	<textarea 
		class="form-control"
		id="validationTextarea"
		placeholder="{control.label}"
		required={control.required}
		aria-describedby="{control.id}-help"
		on:input>{control.value}</textarea>
	{:else}
	<input
		type="{control.type}"
		class="form-control"
		value="{control.value}"
		id="{control.id}"
		required={control.required}
		aria-describedby="{control.id}-help"
		on:input>
	{/if}
	{#if control.helpText}
	<small id="{control.id}-help" class="form-text text-muted">{control.helpText}</small>
	{/if}
</div>
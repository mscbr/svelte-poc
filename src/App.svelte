<script>
	import FeedbackList from './components/feedback-list.svelte';
	import FeedbackStats from './components/feedback-stats.svelte';

	let feedback = [
		{
			id: 1,
			rating: 10,
			text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
		},
		{
			id: 2,
			rating: 9,
			text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
		},
		{
			id: 3,
			rating: 8,
			text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
		}
	];

		$: count = feedback.length;
		$: average = feedback.reduce((a, {rating}) => a + rating, 0) / feedback.length;

		const deleteFeedback = (e) => {
			const itemId = (e.detail);
			feedback = feedback.filter(item => item.id !== itemId);

		};
</script>

<main class="container">
	<FeedbackStats {count} {average}/>
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
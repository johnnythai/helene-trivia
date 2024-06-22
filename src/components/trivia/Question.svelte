<script lang='ts'>
	import { questions } from "$lib/questions";

	const allQuestions: string[] = [];

	// Add easy questions
	allQuestions.push(...questions.easy.map(q => ({ ...q, category: 'easy' })));

	// Add medium questions
	allQuestions.push(...questions.medium.map(q => ({ ...q, category: 'medium' })));

	// Add hard questions
	allQuestions.push(...questions.hard.map(q => ({ ...q, category: 'hard' })));

	console.log(allQuestions);

	let randomQuestion: string;

	const getRandomQuestion = () => {

	}
</script>

<div class="question">
	{allQuestions}
</div>

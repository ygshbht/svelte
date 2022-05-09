<script>
	import FeedbackList from "./components/FeedbackList.svelte"
	import FeedbackForm from "./components/FeedbackForm.svelte"
	import FeedbackStats from "./components/FeedbackStats.svelte"
	let feedback=[
    {
      id: 1,
      rating: 10,
      text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
    },
    {
      id: 2,
      rating: 9,
      text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
    },
    {
      id: 3,
      rating: 8,
      text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
    },
  ]

  $: count = feedback.length
  $: average = feedback.reduce((a,{rating})=>a+rating,0)/feedback.length
  
  const addFeedback = (e)=>{
    const newFeedback =e.detail 
    feedback = [...feedback, newFeedback]
    
  }
</script>

<main class="container">
  <FeedbackForm   />
  <FeedbackStats  />
	<FeedbackList  />
</main>


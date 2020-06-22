<!-- <script> </script> -->
<script>
// components
import Navbar from './Navbar.svelte';
import ExpensesList from './ExpensesList.svelte'
// data
import expensesData from '../public/expenses';

// variables 
let expenses = [...expensesData];
</script>

<Navbar />
<main class="content">
    <ExpensesList expenses={expenses}/>
</main>

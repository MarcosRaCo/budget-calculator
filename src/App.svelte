<script>
// components
import Navbar from './Navbar.svelte';
import ExpensesList from './ExpensesList.svelte'
// data
import expensesData from '../public/expenses';

// variables 
let expenses = [...expensesData];

//funtions
function removeExpense(id) {
    expenses = expenses.filter(item => item.id !== id);

}
</script>

<Navbar />
<main class="content">
    <ExpensesList {expenses} {removeExpense}/>
</main>

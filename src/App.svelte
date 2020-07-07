<script>
// components
import Navbar from './Navbar.svelte';
import ExpensesList from './ExpensesList.svelte'
// data
import expensesData from '../public/expenses';

// variables 
let expenses = [...expensesData];
//reactive
$: total = expenses.reduce((acc,curr)=>{
    return (acc += curr.amount);
})
//funtions
function removeExpense(id) {
    expenses = expenses.filter(item => item.id !== id);

}
function clearExpenses(id) {
    expenses = [];

}
</script>

<Navbar />
<main class="content">
    <ExpensesList {expenses} {removeExpense}/>
    <button type="button" class="btn btn-primary btn-block" on:click={clearExpenses}>clear expenses</button>
</main>

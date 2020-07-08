<script>
// components
import Navbar from './Navbar.svelte';
import ExpensesList from './ExpensesList.svelte';
import Totals from "./Totals.svelte";
// data
import expensesData from '../public/expenses';
// variables 
let expenses = [...expensesData];
// reactive
$: total = expenses.reduce((acc,curr)=>{
    console.log({acc,amount:curr.amount});
    return (acc += curr.amount);
},0)
//funtions
function removeExpense(id) {
    expenses = expenses.filter(item => item.id !== id);

}

function clearExpenses(){
    expenses = [];
}
</script>

<Navbar />
<main class="content">
    <Totals title = "total expenses" {total}/>
    <ExpensesList {expenses} {removeExpense}/>
    <button class="btn btn-primary btn-block" on:click={clearExpenses}>clear expenses</button>
</main>

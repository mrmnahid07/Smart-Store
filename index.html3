<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart Store</title>

<style>
*{box-sizing:border-box}
body{
    margin:0;
    font-family:Arial,"Noto Sans Bengali",sans-serif;
    background:#f1f5f9;
    color:#172033;
}
.sidebar{
    position:fixed;
    left:0;
    top:0;
    bottom:0;
    width:240px;
    background:#111827;
    color:white;
    padding:20px 12px;
}
.logo{
    font-size:23px;
    font-weight:bold;
    padding:10px;
    margin-bottom:15px;
}
.menu{
    width:100%;
    display:block;
    padding:14px;
    margin:5px 0;
    border:0;
    border-radius:8px;
    background:transparent;
    color:white;
    text-align:left;
    font-size:16px;
    cursor:pointer;
}
.menu:hover,.menu.active{
    background:#2563eb;
}

.main{
    margin-left:240px;
    padding:25px;
}

.page{display:none}
.page.active{display:block}

h1,h2,h3{margin-top:0}

.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(190px,1fr));
    gap:15px;
}

.card{
    background:white;
    padding:20px;
    border-radius:12px;
    box-shadow:0 2px 8px #0001;
}

.card h3{
    color:#64748b;
    font-size:14px;
}

.amount{
    font-size:25px;
    font-weight:bold;
}

.panel{
    background:white;
    padding:20px;
    border-radius:12px;
    margin-top:20px;
    box-shadow:0 2px 8px #0001;
}

form{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(190px,1fr));
    gap:14px;
}

label{
    display:block;
    font-weight:bold;
    font-size:14px;
}

input,select,textarea{
    width:100%;
    padding:11px;
    margin-top:6px;
    border:1px solid #cbd5e1;
    border-radius:7px;
    font-size:14px;
}

textarea{min-height:80px}

.full{grid-column:1/-1}

button{
    cursor:pointer;
}

.btn{
    border:0;
    padding:11px 17px;
    border-radius:7px;
    background:#2563eb;
    color:white;
    font-weight:bold;
}

.btn.green{background:#16a34a}
.btn.red{background:#dc2626}
.btn.gray{background:#64748b}

table{
    width:100%;
    border-collapse:collapse;
    min-width:750px;
}

th,td{
    padding:11px;
    border-bottom:1px solid #e2e8f0;
    text-align:left;
}

th{
    background:#f8fafc;
}

.table{
    overflow:auto;
}

.action button{
    border:0;
    padding:6px 9px;
    border-radius:5px;
    color:white;
    margin:2px;
}

.edit{background:#f59e0b}
.delete{background:#dc2626}

.report-card{
    border-left:5px solid #2563eb;
}

.date-filter{
    display:flex;
    gap:10px;
    flex-wrap:wrap;
    align-items:end;
}

.date-filter div{
    min-width:170px;
}

@media(max-width:800px){
    .sidebar{
        width:210px;
    }
    .main{
        margin-left:210px;
        padding:15px;
    }
}

@media(max-width:600px){
    .sidebar{
        position:relative;
        width:100%;
        height:auto;
    }
    .main{
        margin-left:0;
    }
}
</style>
</head>

<body>

<!-- SIDE MENU -->
<div class="sidebar">

<div class="logo">🏪 Smart Store</div>

<button class="menu active" onclick="showPage('dashboard',this)">
🏠 Dashboard
</button>

<button class="menu" onclick="showPage('products',this)">
📦 Products
</button>

<button class="menu" onclick="showPage('sales',this)">
🛒 Sales
</button>

<button class="menu" onclick="showPage('purchase',this)">
🚚 Purchase
</button>

<button class="menu" onclick="showPage('customers',this)">
👥 Customers
</button>

<button class="menu" onclick="showPage('expenses',this)">
💸 Expenses
</button>

<button class="menu" onclick="showPage('reports',this)">
📊 Reports
</button>

</div>


<div class="main">

<!-- DASHBOARD -->
<section id="dashboard" class="page active">

<h1>🏠 Dashboard</h1>

<div class="cards">

<div class="card">
<h3>Total Sales</h3>
<div class="amount" id="dSales">৳0.00</div>
</div>

<div class="card">
<h3>Total Purchase</h3>
<div class="amount" id="dPurchase">৳0.00</div>
</div>

<div class="card">
<h3>Gross Profit</h3>
<div class="amount" id="dGross">৳0.00</div>
</div>

<div class="card">
<h3>Expenses</h3>
<div class="amount" id="dExpense">৳0.00</div>
</div>

<div class="card">
<h3>Net Profit</h3>
<div class="amount" id="dNet">৳0.00</div>
</div>

<div class="card">
<h3>Total Due</h3>
<div class="amount" id="dDue">৳0.00</div>
</div>

<div class="card">
<h3>Stock Value</h3>
<div class="amount" id="dStock">৳0.00</div>
</div>

<div class="card">
<h3>Cash / Balance</h3>
<div class="amount" id="dCash">৳0.00</div>
</div>

</div>

</section>


<!-- PRODUCTS -->
<section id="products" class="page">

<h1>📦 Products</h1>

<div class="panel">

<form id="productForm">

<input type="hidden" id="productId">

<div>
<label>Product Name</label>
<input id="productName" placeholder="Product name" required>
</div>

<div>
<label>Product Code</label>
<input id="productCode" placeholder="Code">
</div>

<div>
<label>Purchase Price</label>
<input id="productBuy" type="number" step="0.01" required>
</div>

<div>
<label>Sale Price</label>
<input id="productSell" type="number" step="0.01" required>
</div>

<div>
<label>Stock</label>
<input id="productStock" type="number" required>
</div>

<div>
<label>Unit</label>
<input id="productUnit" placeholder="pcs / kg">
</div>

<div class="full">

<button class="btn" type="submit">
➕ Add Product
</button>

<button class="btn gray" type="button" onclick="clearProduct()">
Clear
</button>

</div>

</form>

</div>


<div class="panel">

<div class="table">

<table>

<thead>
<tr>
<th>Product</th>
<th>Code</th>
<th>Buy</th>
<th>Sell</th>
<th>Stock</th>
<th>Stock Value</th>
<th>Action</th>
</tr>
</thead>

<tbody id="productList"></tbody>

</table>

</div>

</div>

</section>


<!-- SALES -->
<section id="sales" class="page">

<h1>🛒 Sales</h1>

<div class="panel">

<form id="salesForm">

<div>
<label>Date</label>
<input id="saleDate" type="date" required>
</div>

<div>
<label>Product Name</label>
<input id="saleProduct" placeholder="হাতে Product Name লিখুন" required>
</div>

<div>
<label>Quantity</label>
<input id="saleQty" type="number" min="1" required>
</div>

<div>
<label>Sale Price</label>
<input id="salePrice" type="number" step="0.01" required>
</div>

<div>
<label>Customer</label>
<input id="saleCustomer" placeholder="Customer name">
</div>

<div>
<label>Paid</label>
<input id="salePaid" type="number" step="0.01" value="0">
</div>

<div>
<label>Due</label>
<input id="saleDue" type="number" readonly>
</div>

<div class="full">

<button class="btn green" type="submit">
➕ Add Sale
</button>

</div>

</form>

</div>


<div class="panel">

<h3>Sales History</h3>

<div class="table">

<table>

<thead>
<tr>
<th>Date</th>
<th>Product</th>
<th>Qty</th>
<th>Total</th>
<th>Paid</th>
<th>Due</th>
<th>Customer</th>
<th>Action</th>
</tr>
</thead>

<tbody id="salesList"></tbody>

</table>

</div>

</div>

</section>


<!-- PURCHASE -->
<section id="purchase" class="page">

<h1>🚚 Purchase</h1>

<div class="panel">

<form id="purchaseForm">

<div>
<label>Date</label>
<input id="purchaseDate" type="date" required>
</div>

<div>
<label>Product Name</label>
<input id="purchaseProduct" placeholder="Product name" required>
</div>

<div>
<label>Quantity</label>
<input id="purchaseQty" type="number" min="1" required>
</div>

<div>
<label>Purchase Price</label>
<input id="purchasePrice" type="number" step="0.01" required>
</div>

<div>
<label>Supplier</label>
<input id="purchaseSupplier" placeholder="Supplier">
</div>

<div class="full">

<button class="btn" type="submit">
➕ Add Purchase
</button>

</div>

</form>

</div>


<div class="panel">

<div class="table">

<table>

<thead>
<tr>
<th>Date</th>
<th>Product</th>
<th>Qty</th>
<th>Price</th>
<th>Total</th>
<th>Supplier</th>
<th>Action</th>
</tr>
</thead>

<tbody id="purchaseList"></tbody>

</table>

</div>

</div>

</section>


<!-- CUSTOMERS -->
<section id="customers" class="page">

<h1>👥 Customers</h1>

<div class="panel">

<form id="customerForm">

<div>
<label>Customer Name</label>
<input id="customerName" required>
</div>

<div>
<label>Mobile</label>
<input id="customerMobile">
</div>

<div>
<label>Address</label>
<input id="customerAddress">
</div>

<div>
<label>Opening Due</label>
<input id="customerDue" type="number" step="0.01" value="0">
</div>

<div>
<label>Payment</label>
<input id="customerPayment" type="number" step="0.01" value="0">
</div>

<div class="full">

<button class="btn" type="submit">
➕ Add Customer
</button>

</div>

</form>

</div>


<div class="panel">

<div class="table">

<table>

<thead>
<tr>
<th>Name</th>
<th>Mobile</th>
<th>Address</th>
<th>Due</th>
<th>Action</th>
</tr>
</thead>

<tbody id="customerList"></tbody>

</table>

</div>

</div>

</section>


<!-- EXPENSE -->
<section id="expenses" class="page">

<h1>💸 Expenses</h1>

<div class="panel">

<form id="expenseForm">

<div>
<label>Date</label>
<input id="expenseDate" type="date" required>
</div>

<div>
<label>Expense Name</label>
<input id="expenseName" required>
</div>

<div>
<label>Amount</label>
<input id="expenseAmount" type="number" step="0.01" required>
</div>

<div class="full">
<label>Note</label>
<textarea id="expenseNote"></textarea>
</div>

<div>

<button class="btn" type="submit">
➕ Add Expense
</button>

</div>

</form>

</div>


<div class="panel">

<div class="table">

<table>

<thead>
<tr>
<th>Date</th>
<th>Expense</th>
<th>Amount</th>
<th>Note</th>
<th>Action</th>
</tr>
</thead>

<tbody id="expenseList"></tbody>

</table>

</div>

</div>

</section>


<!-- REPORTS -->
<section id="reports" class="page">

<h1>📊 Business Reports</h1>

<div class="panel">

<h3>📅 Date Filter</h3>

<div class="date-filter">

<div>
<label>From Date</label>
<input type="date" id="fromDate">
</div>

<div>
<label>To Date</label>
<input type="date" id="toDate">
</div>

<div>
<button class="btn" onclick="filterReport()">
🔍 View Report
</button>
</div>

<div>
<button class="btn gray" onclick="resetReport()">
All
</button>
</div>

</div>

</div>


<div class="cards">

<div class="card report-card">
<h3>Total Sales</h3>
<div class="amount" id="rSales">৳0.00</div>
</div>

<div class="card report-card">
<h3>Total Purchase</h3>
<div class="amount" id="rPurchase">৳0.00</div>
</div>

<div class="card report-card">
<h3>Gross Profit</h3>
<div class="amount" id="rGross">৳0.00</div>
</div>

<div class="card report-card">
<h3>Expenses</h3>
<div class="amount" id="rExpenses">৳0.00</div>
</div>

<div class="card report-card">
<h3>Net Profit</h3>
<div class="amount" id="rNet">৳0.00</div>
</div>

<div class="card report-card">
<h3>Total Due</h3>
<div class="amount" id="rDue">৳0.00</div>
</div>

<div class="card report-card">
<h3>Stock Value</h3>
<div class="amount" id="rStock">৳0.00</div>
</div>

<div class="card report-card">
<h3>Cash / Balance</h3>
<div class="amount" id="rCash">৳0.00</div>
</div>

<div class="card report-card">
<h3>Total Products</h3>
<div class="amount" id="rProducts">0</div>
</div>

</div>

</section>

</div>


<script>

/* =========================
   DATABASE
========================= */

let db = JSON.parse(
localStorage.getItem("smartStoreDB")
) || {
products:[],
sales:[],
purchases:[],
customers:[],
expenses:[]
};

function save(){
localStorage.setItem(
"smartStoreDB",
JSON.stringify(db)
);
renderAll();
}

function money(n){
return "৳" + Number(n || 0).toFixed(2);
}

function today(){
return new Date().toISOString().split("T")[0];
}


/* =========================
   MENU
========================= */

function showPage(id,button){

document.querySelectorAll(".page")
.forEach(p=>p.classList.remove("active"));

document.getElementById(id)
.classList.add("active");

document.querySelectorAll(".menu")
.forEach(b=>b.classList.remove("active"));

button.classList.add("active");

}


/* =========================
   PRODUCT
========================= */

productForm.addEventListener("submit",function(e){

e.preventDefault();

let id=productId.value;

let product={
id:id || Date.now().toString(),
name:productName.value.trim(),
code:productCode.value.trim(),
buy:Number(productBuy.value),
sell:Number(productSell.value),
stock:Number(productStock.value),
unit:productUnit.value.trim(),
date:today()
};

if(id){

let old=db.products.find(p=>p.id===id);

if(old){
Object.assign(old,product);
}

}else{

db.products.push(product);

}

clearProduct();

save();

});


function clearProduct(){

productId.value="";
productName.value="";
productCode.value="";
productBuy.value="";
productSell.value="";
productStock.value="";
productUnit.value="";

}


function editProduct(id){

let p=db.products.find(x=>x.id===id);

if(!p)return;

productId.value=p.id;
productName.value=p.name;
productCode.value=p.code;
productBuy.value=p.buy;
productSell.value=p.sell;
productStock.value=p.stock;
productUnit.value=p.unit;

showPage(
"products",
document.querySelectorAll(".menu")[1]
);

}


function deleteProduct(id){

if(!confirm("Product delete করবেন?"))return;

db.products=
db.products.filter(p=>p.id!==id);

save();

}


function renderProducts(){

productList.innerHTML="";

db.products.forEach(p=>{

productList.innerHTML+=`

<tr>

<td>${p.name}</td>

<td>${p.code}</td>

<td>${money(p.buy)}</td>

<td>${money(p.sell)}</td>

<td>${p.stock} ${p.unit}</td>

<td>${money(p.stock*p.buy)}</td>

<td class="action">

<button class="edit"
onclick="editProduct('${p.id}')">
Edit
</button>

<button class="delete"
onclick="deleteProduct('${p.id}')">
Delete
</button>

</td>

</tr>

`;

});

}


/* =========================
   SALES
========================= */

saleDate.value=today();

salePaid.addEventListener("input",calculateSaleDue);
saleQty.addEventListener("input",calculateSaleDue);
salePrice.addEventListener("input",calculateSaleDue);

function calculateSaleDue(){

let total=
Number(saleQty.value||0)*
Number(salePrice.value||0);

let paid=
Number(salePaid.value||0);

saleDue.value=
Math.max(0,total-paid).toFixed(2);

}


salesForm.addEventListener("submit",function(e){

e.preventDefault();

let name=saleProduct.value.trim();
let qty=Number(saleQty.value);
let price=Number(salePrice.value);
let paid=Number(salePaid.value||0);

let total=qty*price;
let due=Math.max(0,total-paid);

if(paid>total){

alert("Paid amount বেশি হতে পারবে না।");
return;

}


/* Product খুঁজবে */

let product=db.products.find(
p=>p.name.toLowerCase()===name.toLowerCase()
);

let cost=0;

/*
যদি Product থাকে:
Stock কমবে
Purchase price দিয়ে profit হিসাব হবে
*/

if(product){

if(product.stock<qty){

alert("Stock পর্যাপ্ত নেই।");
return;

}

cost=qty*product.buy;

product.stock-=qty;

}else{

/*
Product আগে না থাকলেও
হাতে লিখে Sale করা যাবে।
*/
cost=0;

}


db.sales.push({

id:Date.now().toString(),

date:saleDate.value,

product:name,

qty:qty,

price:price,

total:total,

paid:paid,

due:due,

customer:saleCustomer.value.trim(),

cost:cost

});


salesForm.reset();

saleDate.value=today();

save();

});


function deleteSale(id){

if(!confirm("এই Sale Delete করবেন?"))return;

let sale=db.sales.find(x=>x.id===id);

if(!sale)return;


/*
Sale Delete করলে Product-এর stock ফেরত যাবে
*/

let product=db.products.find(
p=>p.name.toLowerCase()===sale.product.toLowerCase()
);

if(product){
product.stock+=sale.qty;
}

db.sales=
db.sales.filter(x=>x.id!==id);

save();

}


function renderSales(){

salesList.innerHTML="";

db.sales.slice().reverse().forEach(s=>{

salesList.innerHTML+=`

<tr>

<td>${s.date}</td>

<td>${s.product}</td>

<td>${s.qty}</td>

<td>${money(s.total)}</td>

<td>${money(s.paid)}</td>

<td>${money(s.due)}</td>

<td>${s.customer||"-"}</td>

<td class="action">

<button class="delete"
onclick="deleteSale('${s.id}')">
Delete
</button>

</td>

</tr>

`;

});

}


/* =========================
   PURCHASE
========================= */

purchaseDate.value=today();

purchaseForm.addEventListener("submit",function(e){

e.preventDefault();

let name=purchaseProduct.value.trim();
let qty=Number(purchaseQty.value);
let price=Number(purchasePrice.value);

let product=db.products.find(
p=>p.name.toLowerCase()===name.toLowerCase()
);

if(product){

/*
Purchase করলে Stock +
*/

product.stock+=qty;

/*
Average purchase price update
*/

let oldStock=product.stock-qty;

if(oldStock+qty>0){

product.buy=
(
(product.buy*oldStock)+(price*qty)
)/
(oldStock+qty);

}

}else{

/*
নতুন Product হলে automatic create
*/

db.products.push({

id:Date.now().toString(),

name:name,

code:"",

buy:price,

sell:price,

stock:qty,

unit:"pcs",

date:purchaseDate.value

});

}


db.purchases.push({

id:Date.now().toString(),

date:purchaseDate.value,

product:name,

qty:qty,

price:price,

total:qty*price,

supplier:purchaseSupplier.value.trim()

});


purchaseForm.reset();

purchaseDate.value=today();

save();

});


function deletePurchase(id){

if(!confirm("Purchase Delete করবেন?"))return;

let p=db.purchases.find(x=>x.id===id);

if(!p)return;

let product=db.products.find(
x=>x.name.toLowerCase()===p.product.toLowerCase()
);

if(product){

product.stock-=p.qty;

}

db.purchases=
db.purchases.filter(x=>x.id!==id);

save();

}


function renderPurchases(){

purchaseList.innerHTML="";

db.purchases.slice().reverse().forEach(p=>{

purchaseList.innerHTML+=`

<tr>

<td>${p.date}</td>
<td>${p.product}</td>
<td>${p.qty}</td>
<td>${money(p.price)}</td>
<td>${money(p.total)}</td>
<td>${p.supplier||"-"}</td>

<td>

<button class="delete"
onclick="deletePurchase('${p.id}')">
Delete
</button>

</td>

</tr>

`;

});

}


/* =========================
   CUSTOMERS
========================= */

customerForm.addEventListener("submit",function(e){

e.preventDefault();

let due=
Number(customerDue.value||0)-
Number(customerPayment.value||0);

db.customers.push({

id:Date.now().toString(),

name:customerName.value.trim(),

mobile:customerMobile.value.trim(),

address:customerAddress.value.trim(),

due:Math.max(0,due),

date:today()

});

customerForm.reset();

customerDue.value=0;
customerPayment.value=0;

save();

});


function deleteCustomer(id){

if(!confirm("Customer Delete করবেন?"))return;

db.customers=
db.customers.filter(x=>x.id!==id);

save();

}


function renderCustomers(){

customerList.innerHTML="";

db.customers.forEach(c=>{

customerList.innerHTML+=`

<tr>

<td>${c.name}</td>
<td>${c.mobile||"-"}</td>
<td>${c.address||"-"}</td>
<td>${money(c.due)}</td>

<td>

<button class="delete"
onclick="deleteCustomer('${c.id}')">
Delete
</button>

</td>

</tr>

`;

});

}


/* =========================
   EXPENSE
========================= */

expenseDate.value=today();

expenseForm.addEventListener("submit",function(e){

e.preventDefault();

db.expenses.push({

id:Date.now().toString(),

date:expenseDate.value,

name:expenseName.value.trim(),

amount:Number(expenseAmount.value),

note:expenseNote.value.trim()

});

expenseForm.reset();

expenseDate.value=today();

save();

});


function deleteExpense(id){

if(!confirm("Expense Delete করবেন?"))return;

db.expenses=
db.expenses.filter(x=>x.id!==id);

save();

}


function renderExpenses(){

expenseList.innerHTML="";

db.expenses.slice().reverse().forEach(e=>{

expenseList.innerHTML+=`

<tr>

<td>${e.date}</td>
<td>${e.name}</td>
<td>${money(e.amount)}</td>
<td>${e.note||"-"}</td>

<td>

<button class="delete"
onclick="deleteExpense('${e.id}')">
Delete
</button>

</td>

</tr>

`;

});

}


/* =========================
   REPORT
========================= */

function calculateReport(from=null,to=null){

let sales=db.sales;
let purchases=db.purchases;
let expenses=db.expenses;

if(from && to){

sales=sales.filter(x=>x.date>=from&&x.date<=to);

purchases=purchases.filter(x=>x.date>=from&&x.date<=to);

expenses=expenses.filter(x=>x.date>=from&&x.date<=to);

}


let totalSales=
sales.reduce((a,x)=>a+x.total,0);

let totalPurchase=
purchases.reduce((a,x)=>a+x.total,0);

let cost=
sales.reduce((a,x)=>a+x.cost,0);

let totalExpenses=
expenses.reduce((a,x)=>a+x.amount,0);

let gross=
totalSales-cost;

let net=
gross-totalExpenses;

let salesDue=
sales.reduce((a,x)=>a+x.due,0);

let customerDue=
db.customers.reduce((a,x)=>a+x.due,0);

let totalDue=
salesDue+customerDue;

let stockValue=
db.products.reduce(
(a,x)=>a+(x.stock*x.buy),0
);


/*
Cash:
Sales Paid
- Purchase
- Expenses
*/

let paid=
sales.reduce((a,x)=>a+x.paid,0);

let cash=
paid-totalPurchase-totalExpenses;


return{
totalSales,
totalPurchase,
gross,
totalExpenses,
net,
totalDue,
stockValue,
cash
};

}


function showReport(data){

rSales.textContent=money(data.totalSales);
rPurchase.textContent=money(data.totalPurchase);
rGross.textContent=money(data.gross);
rExpenses.textContent=money(data.totalExpenses);
rNet.textContent=money(data.net);
rDue.textContent=money(data.totalDue);
rStock.textContent=money(data.stockValue);
rCash.textContent=money(data.cash);
rProducts.textContent=db.products.length;

}


/*
Dashboard
*/

function updateDashboard(){

let d=calculateReport();

dSales.textContent=money(d.totalSales);
dPurchase.textContent=money(d.totalPurchase);
dGross.textContent=money(d.gross);
dExpense.textContent=money(d.totalExpenses);
dNet.textContent=money(d.net);
dDue.textContent=money(d.totalDue);
dStock.textContent=money(d.stockValue);
dCash.textContent=money(d.cash);

showReport(d);

}


/* Date Report */

function filterReport(){

let from=fromDate.value;
let to=toDate.value;

if(!from||!to){

alert("From এবং To Date নির্বাচন করুন।");
return;

}

showReport(
calculateReport(from,to)
);

}


function resetReport(){

fromDate.value="";
toDate.value="";

showReport(
calculateReport()
);

}


/* =========================
   RENDER ALL
========================= */

function renderAll(){

renderProducts();

renderSales();

renderPurchases();

renderCustomers();

renderExpenses();

updateDashboard();

}


/* =========================
   START
========================= */

renderAll();

</script>

</body>
</html>

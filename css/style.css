var productNameInput = document.getElementById("productName")
var productPriceInput = document.getElementById("productPrice")
var productCategoryInput = document.getElementById("productCategory")
var productDescriptionInput = document.getElementById("productDescription")
var searchInput = document.getElementById("searchInput")
var productList;
var currentIndex = 0
if (localStorage.getItem("list") != null) {
    productList = JSON.parse(localStorage.getItem("list"))
    displayData()
}
else {
    productList = []
}


function addProduct() {

    if (validName() && validPrice()) {

        var product = {
            name: productNameInput.value,
            price: productPriceInput.value,
            category: productCategoryInput.value,
            desc: productDescriptionInput.value
        }
        productList.push(product)
        localStorage.setItem("list", JSON.stringify(productList))
        displayData()
    }

}

function displayData() {
    var temp = "";
    for (var i = 0; i < productList.length; i++) {
        temp += `<tr>
        <td>`+ i + `</td>
        <td>`+ productList[i].name + `</td>
        <td>`+ productList[i].price + `</td>
        <td>`+ productList[i].category + `</td>
        <td>`+ productList[i].desc + `</td>
        <td>
            <button class="btn btn-outline-warning"  onclick="updateData(`+ i + `)">update</button>
        </td>
        <td>
            <button class="btn btn-outline-danger" onclick="deleteProduct(`+ i + `)" >delete</button>
        </td>
    </tr>
   `
    }
    document.getElementById("tableData").innerHTML = temp
}
function deleteProduct(index) {
    productList.splice(index, 1)
    localStorage.setItem("list", JSON.stringify(productList))
    displayData()
}




function updateData(index) { //local
    currentIndex = index
    productNameInput.value = productList[index].name
    productPriceInput.value = productList[index].price
    productDescriptionInput.value = productList[index].desc
    productCategoryInput.value = productList[index].category


    document.getElementById("EditBtn").style.display = "inline"
    document.getElementById("addBtn").style.display = "none"
}

function addEdit() {

    console.log(currentIndex);
    productList[currentIndex].name = productNameInput.value
    productList[currentIndex].price = productPriceInput.value
    productList[currentIndex].desc = productDescriptionInput.value
    productList[currentIndex].category = productCategoryInput.value
    localStorage.setItem("list", JSON.stringify(productList))
    displayData()
    document.getElementById("EditBtn").style.display = "none"
    document.getElementById("addBtn").style.display = "inline"
}

function clearForm() {

    productNameInput.value = ""
    productPriceInput.value = ""
    productDescriptionInput.value = ""
    productCategoryInput.value = ""
}



function search() {
    var searchValue = searchInput.value;
    var cartona = ""
    for (var i = 0; i < productList.length; i++) {
        if (productList[i].name.toLowerCase().includes(searchValue.toLowerCase())
            ||
            productList[i].category.toLowerCase().includes(searchValue.toLowerCase())
        ) {
            cartona += `<tr>
            <td>`+ i + `</td>
            <td>`+ productList[i].name.replace(searchValue, "<span class='text-danger'>" + searchValue + "</span>") + `</td>
            <td>`+ productList[i].price + `</td>
            <td>`+ productList[i].category.replace(searchValue, "<span class='text-danger'>" + searchValue + "</span>") + `</td>
            <td>`+ productList[i].desc + `</td>
            <td>
                <button class="btn btn-outline-warning"  onclick="updateData(`+ i + `)">update</button>
            </td>
            <td>
                <button class="btn btn-outline-danger" onclick="deleteProduct(`+ i + `)" >delete</button>
            </td>
        </tr>
       `
        }
    }

    document.getElementById("tableData").innerHTML = cartona
}













function validName() {
    var validTest = false
    var regex = /^[A-Z][a-z]{3,8}[0-9]?$/;
    if (regex.test(productNameInput.value)) {
        console.log("tmam");
        document.getElementById("alertName").style.display = "none";
        validTest = true
    }
    else {
        console.log("invalid");
        document.getElementById("alertName").style.display = "block";
        validTest = false
    }

    return validTest
}
function validPrice() {

    var testValid = false
    var regex = /^[0-9]{3,5}$/;
    if (regex.test(productPriceInput.value)) {
        console.log("tmam");
        document.getElementById("alertPrice").style.display = "none";
        testValid = true
    }
    else {
        console.log("invalid");
        document.getElementById("alertPrice").style.display = "block";
        testValid = false
    }

    return testValid
}
## D287 JAVA FRAMEWORKS: Read Me

**Scenario**:
You are working for a company that licenses and customizes a software application to keep track of inventory 
in stores. Your job as a software developer is to customize this application to meet a specific customer’s 
needs. You will choose any type of customer you would like, but it must sell a product composed of parts. You 
are working for a company that licenses and customizes a software application to keep track of inventory 
in stores. Your job as a software developer is to customize this application to meet a specific customer’s 
needs. You will choose any type of customer you would like, but it must sell a product composed of parts.

For my project, I created a Computer Storefront where customers can choose between laptops and desktops, 
then customize their build by selecting components such as the processor, RAM, storage, graphics card, and 
PC case. The store also offers prebuilt systems assembled in-house, providing a convenient option for those 
who want a ready-to-use computer. This setup gives customers the flexibility to either fully customize their
PC or purchase a professionally built system.  

## TRACKED CHANGES

**C.  Customize the HTML user interface for your customer’s application. The user interface should include the 
shop name, the product names, and the names of the parts:**

**filename: style.css**

**lines added 1-80 for the styling of the mainscreen it refers to mainscreen.html file (added background picture, background color, font color
and animations)**

/* css styling file for background color, fonts and animations */
.Background{
width: 100%;
min-height: 100vh;
background-image: url("../images/technology.jpg");
background-size: cover;
background-position: center;
position: relative;
overflow: hidden;
}
.container {
position: relative;
z-index: 1;
}
.lines img{
height: 100px;
width: 50px;
animation: line 7s linear infinite ;
bottom: -500px;
}
.lines {
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
display: flex;
align-items: flex-end;
justify-content: space-around;
bottom: -500px;
}
@keyframes line {
0% {
transform: translate(0px, 120%);
opacity: 0;
}
10% {
opacity: 1;
}
50% {
transform: translate(0, 0);
opacity: 1;
}
100% {
transform: translate(0px, -100vh);
opacity: 0;
}
}
.lines img:nth-child(1){
animation-delay: -2s;
}
.lines img:nth-child(2){
animation-delay: -1s;
}
.lines img:nth-child(3){
animation-delay: -3s;
}
.lines img:nth-child(4){
animation-delay: -2s;
}
.lines img:nth-child(5){
animation-delay: -3s;
}
.lines img:nth-child(6){
animation-delay: -3s;
}
.lines img:nth-child(7){
animation-delay: -2s;
}
h1 {
color: white;
}
h2 {
color: white;
}
form {
color: white;
}
th {
color: white;
}

**filename: mainscreen.html**

**line 14: changed the name of the store to computer store.**

<title>Computer Store</title>

**line 15: mainscreen.html reference link command for the html file to refer to css file**

<link rel="stylesheet" href="/css/style.css">    <!-- added reference file for html website styling -->


**lines 18 and 99: class surrounds container class to display background, to not overlap buttons.**

<div class="Background" >  <!-- added class for html website styling reference to style.css -->

</div>

**lines 19-27: added lines class with images for animation on the mainscreen webpage for styling.**

<div class="lines">
<img src="/images/neonline.png" alt="lines Logo">
<img src="/images/neonline.png" alt="lines Logo">
<img src="/images/neonline.png" alt="lines Logo">
<img src="/images/neonline.png" alt="lines Logo">
<img src="/images/neonline.png" alt="lines Logo">
<img src="/images/neonline.png" alt="lines Logo">
<img src="/images/neonline.png" alt="lines Logo">
</div>

**line 31: modify header name changed to PC parts**

<h2>PC Parts</h2>

**line 63: modify header name changed to PC builds**

<h2>PC Builds</h2>

**D. Add an “About” page to the application to describe your chosen customer’s company to web viewers and include 
navigation to and from the “About” page and the main screen.**

**filename: mainscreen.html**

**line 30-34: added a button linked to the About Us page, under the title of the website**

<div class="AboutButton">  <!-- class creation for the button -->
<a href="/about">      <!-- for reference to the MainScreenControllerr java file -->
<button type="button">About Us</button>  <!-- button creation for mainscreen shows About Us -->
</a>
</div>

**filename: MainScreenControllerr.java**

**line 55-58: added controller @GetMapping to allow access to About Us page when the button is clicked**

@GetMapping("/about")
public String about() {
return "about";  // loads about.html from templates
}

**filename: about.html**

**line 1-101: added new file about.html and css styling kept the same from the mainscreen page, added brief
description of the company and the business front. Added class Mainbutton, to have a button from the about us page 
to navigate back to the mainscreen**

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>About Us</title>
    <style>
        /* css styling file for background color, fonts and animations */
        .Background{
            width: 100%;
            min-height: 100vh;
            background-image: url("/images/technology.jpg");
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }
        .container {
            position: relative;
            z-index: 1;
        }
        .lines img{
            height: 100px;
            width: 50px;
            animation: line 7s linear infinite ;
            bottom: -500px;
        }
        .lines {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: flex-end;
            justify-content: space-around;
            bottom: -500px;
        }
        .page-align {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 25vh;
            text-align: center;
            width: 60%;
            margin: 0 auto;
            line-height: 1.6;
        }
        @keyframes line {
            0% { transform: translate(0px, 120%); opacity: 0; }
            10% { opacity: 1; }
            50% { transform: translate(0, 0); opacity: 1; }
            100% { transform: translate(0px, -100vh); opacity: 0; }
        }
        .lines img:nth-child(1){ animation-delay: -2s; }
        .lines img:nth-child(2){ animation-delay: -1s; }
        .lines img:nth-child(3){ animation-delay: -3s; }
        .lines img:nth-child(4){ animation-delay: -2s; }
        .lines img:nth-child(5){ animation-delay: -3s; }
        .lines img:nth-child(6){ animation-delay: -3s; }
        .lines img:nth-child(7){ animation-delay: -2s; }
        h1, h2, form, th, p { color: white; }
    </style>
</head>
<body class="Background">
<div class="container">
    <h1>About Us</h1>
 <div class="MainButton">  <!-- class creation for the button -->
        <a href="/mainscreen">      <!-- for reference to the MainScreenControllerr java file -->
            <button type="button">Back to Mainscreen</button> <!-- button creation for navigation mainscreen -->
        </a>
    </div>
    <h2>Welcome to our computer store</h2>
    <div class="page-align"> <!-- class creation for text alignment on page -->
    <p>
        Welcome to our computer store, your one-stop destination for custom-built PCs, high-quality components, and
        prebuilt systems. We help customers design their ideal computing setup—whether it’s a powerful desktop for
        gaming, a workstation for creative projects, a reliable personal computer for everyday use, or a sleek laptop
        for portability. Our mission is to provide top-quality products, friendly customer service, and expert guidance
        to ensure you get the perfect PC tailored to your needs.
    </p>
    </div>
    <hr>
    <h2>My Products</h2>
    <div class="page-align">
    <p>
        Our business makes it easy for customers to get the perfect PC. Whether you prefer a laptop or desktop, you
        can customize your system by choosing from a range of components, including processors, RAM, storage,
        graphics cards, and cases. For those who want a hassle-free experience, we also offer prebuilt computers
        assembled in-house, ready to use right out of the box. Our store is designed to give every customer the choice
        between a fully personalized PC build or a professionally assembled system that delivers performance and
        reliability.
    </p>
    </div>
    <hr>
</div>
<div class="lines">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
</div>
</body>
</html>

**E. Add a sample inventory appropriate for your chosen store to the application. You should have five parts and five products in your sample inventory and should not overwrite existing data in the database.**

**filename: BootStrapData.java**

**line 31,34,36: added code inhouse repository to public class for the creation of the five parts and five products**

@Component
public class BootStrapData implements CommandLineRunner {

    private final ProductRepository productRepository;
    private final InhousePartRepository inhousePartRepository;
    private final OutsourcedPartRepository outsourcedPartRepository;

    public BootStrapData(PartRepository partRepository, ProductRepository productRepository, OutsourcedPartRepository outsourcedPartRepository, InhousePartRepository inhousePartRepository) {
        this.productRepository = productRepository;
        this.inhousePartRepository = inhousePartRepository;
        this.outsourcedPartRepository=outsourcedPartRepository;
    }

**line 43-112: added 5 new parts to the repository (2 in-house and 3 outsourced) and added 5 products**

    if (inhousePartRepository.count() == 0) {

        // creating object from class InHousePart
        InhousePart CPU = new InhousePart();
        // setting the value for object
        CPU.setName("AMD Ryzen 7 9800X3D");
        CPU.setInv(25);
        CPU.setPrice(479.99);
        CPU.setId(5);
        inhousePartRepository.save(CPU);

        // creating object from class InHousePart
        InhousePart Ram = new InhousePart();
        // setting the value for object
        Ram.setName("G.Skill Trident Z5 Royal Neo DDR5 (2x16GB) 32GB");
        Ram.setInv(28);
        Ram.setPrice(154.99);
        Ram.setId(8);
        inhousePartRepository.save(Ram);
    }

        if (outsourcedPartRepository.count() == 0){

        // creating object from class OutsourcedPart
        OutsourcedPart GPU = new OutsourcedPart();
        // setting the value for object
        GPU.setCompanyName("NVIDIA");
        GPU.setName("RTX 5070 12GB");
        GPU.setInv(20);
        GPU.setPrice(549.99);
        GPU.setId(7);
        outsourcedPartRepository.save(GPU);

        // creating object from class OutsourcedPart
        OutsourcedPart NVMe = new OutsourcedPart();
        // setting the value for object
        NVMe.setCompanyName("Western Digital");
        NVMe.setName("2TB NVMe PCIe 4.0 Internal M.2 SSD");
        NVMe.setInv(10);
        NVMe.setPrice(119.99);
        NVMe.setId(4);
        outsourcedPartRepository.save(NVMe);

        // creating object from class OutsourcedPart
        OutsourcedPart TowerCase = new OutsourcedPart();
        // setting the value for object
        TowerCase.setCompanyName("NZXT");
        TowerCase.setName("H9 Flow ATX mid-tower PC case");
        TowerCase.setInv(10);
        TowerCase.setPrice(99.99);
        TowerCase.setId(2);
        outsourcedPartRepository.save(TowerCase);
    }
        if(productRepository.count() == 0) {
            // creating an object from the product class
            Product GamingPC = new Product(15,"Gaming PC Build", 1799.99, 3 );
            productRepository.save(GamingPC);
            // creating an object from the product class
            Product OfficePC = new Product(11,"Office Desktop", 999.99, 5 );
            productRepository.save(OfficePC);
            // creating an object from the product class
            Product studentLaptop = new Product(14,"Student Laptop", 799.99, 3 );
            productRepository.save(studentLaptop);
            // creating an object from the product class
            Product creatorPC = new Product(13,"Content Creator Desktop", 2199.99, 2 );
            productRepository.save(creatorPC);
            // creating an object from the product class
            Product budgetPC = new Product(16,"Budget Desktop", 499.99, 4 );
            productRepository.save(budgetPC);
        }
    }
}

**filename: style.css**

**line 79-84: styling font white for the table containing the parts and products**

/* overriding styling colors for table to white only */
.table td {
color: white !important;
}
.table th {
color: white !important;
}

**F.  Add a “Buy Now” button to your product list**

**filename: mainscreen.html**

**line 100: added new button to product table called Buy Now**

<a th:href="@{/BuyProduct(productID=${tempProduct.id})}" class="btn btn-primary btn-sm mb-3">Buy Now</a>

**filename: AddProductController.java**

**line 176-204: Created @GetMapping BuyProduct method to check if the purchased object is in stock.
              If in product is in stock it redirects to Success.html and reduces the inventory by 1,
              on the contrary the product is not available it redirects to failure.html**

    @GetMapping("/BuyProduct")
    public String BuyProduct(@RequestParam("productID") int theId, Model theModel) {
        // initialize product service through spring context
        ProductService productService = context.getBean(ProductServiceImpl.class);
        // creating a product object
        Product product2=productService.findById(theId);
        // create variable to store the value of inventory
        int inv = product2.getInv();
        // checking for if inv value is 0
        if(inv == 0)
        {
            // returning failure.html page
            return "Failure";
        }
        else
        {
            // ADD CODE TO DECREMENT THE INV BY 1
            inv = inv - 1;
            // SET NEW VALUE FOR INV
            product2.setInv(inv);
            // SAVE PRODUCT OBJECT WITH NEW INV VALUE
            productService.save(product2);

            // returning Success.html page
            return "Success";
        }

    }

**filename: Failure.html**

**line 1-80: added Failure.html file to display failure of purchase of the product, using the same styling
           as the style.css file for the background of the page**

<!DOCTYPE html>
<html lang="en">
<head>
    <title>Failure</title>
    <style>
        /* css styling file for background color, fonts and animations */
        .Background{
            width: 100%;
            min-height: 100vh;
            background-image: url("/images/technology.jpg");
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }
        .container {
            position: relative;
            z-index: 1;
        }
        .lines img{
            height: 100px;
            width: 50px;
            animation: line 7s linear infinite ;
            bottom: -500px;
        }
        .lines {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: flex-end;
            justify-content: space-around;
            bottom: -500px;
        }
        .page-align {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 25vh;
            text-align: center;
            width: 60%;
            margin: 0 auto;
            line-height: 1.6;
        }
        @keyframes line {
            0% { transform: translate(0px, 120%); opacity: 0; }
            10% { opacity: 1; }
            50% { transform: translate(0, 0); opacity: 1; }
            100% { transform: translate(0px, -100vh); opacity: 0; }
        }
        .lines img:nth-child(1){ animation-delay: -2s; }
        .lines img:nth-child(2){ animation-delay: -1s; }
        .lines img:nth-child(3){ animation-delay: -3s; }
        .lines img:nth-child(4){ animation-delay: -2s; }
        .lines img:nth-child(5){ animation-delay: -3s; }
        .lines img:nth-child(6){ animation-delay: -3s; }
        .lines img:nth-child(7){ animation-delay: -2s; }
        h1, h2, form, th, p { color: white; }
    </style>
</head>
<body class="Background">
<div class="container">
<h1>Purchase failed please try again</h1>

<a href="http://localhost:8080/">Link
to Main Screen</a>
</div>
<div class="lines">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
</div>
</body>
</html>

**filename: Success.html**

**line 1-80: added Success.html file to display success of purchase of the product, using the same styling
as the style.css file for the background of the page**

<!DOCTYPE html>
<html lang="en">
<head>
    <title>Success</title>
    <style>
        /* css styling file for background color, fonts and animations */
        .Background{
            width: 100%;
            min-height: 100vh;
            background-image: url("/images/technology.jpg");
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }
        .container {
            position: relative;
            z-index: 1;
        }
        .lines img{
            height: 100px;
            width: 50px;
            animation: line 7s linear infinite ;
            bottom: -500px;
        }
        .lines {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: flex-end;
            justify-content: space-around;
            bottom: -500px;
        }
        .page-align {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 25vh;
            text-align: center;
            width: 60%;
            margin: 0 auto;
            line-height: 1.6;
        }
        @keyframes line {
            0% { transform: translate(0px, 120%); opacity: 0; }
            10% { opacity: 1; }
            50% { transform: translate(0, 0); opacity: 1; }
            100% { transform: translate(0px, -100vh); opacity: 0; }
        }
        .lines img:nth-child(1){ animation-delay: -2s; }
        .lines img:nth-child(2){ animation-delay: -1s; }
        .lines img:nth-child(3){ animation-delay: -3s; }
        .lines img:nth-child(4){ animation-delay: -2s; }
        .lines img:nth-child(5){ animation-delay: -3s; }
        .lines img:nth-child(6){ animation-delay: -3s; }
        .lines img:nth-child(7){ animation-delay: -2s; }
        h1, h2, form, th, p { color: white; }
    </style>
</head>
<body class="Background">
<div class="container">
    <h1>Purchase was successful</h1>

    <a href="http://localhost:8080/">Link
        to Main Screen</a>
</div>
<div class="lines">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
    <img src="/images/neonline.png" alt="lines logo">
</div>
</body>
</html>     

**G. Modify the parts to track maximum and minimum inventory by doing the following:
•  Add additional fields to the part entity for maximum and minimum inventory.
•  Modify the sample inventory to include the maximum and minimum fields.
•  Add to the InhousePartForm and OutsourcedPartForm forms additional text inputs for the inventory so the user can set the maximum and minimum values.
•  Rename the file the persistent storage is saved to.
•  Modify the code to enforce that the inventory is between or at the minimum and maximum value.**

**filename: Part.java**

**line 23: inserted validator rule to enforce that inventory is between min and max**

@ValidInventory

**line 33-36: declared two new variables (MinInv and MaxInv) using @Min annotation, enforced that the value must be
a positive integer**

@Min(value = 0, message = "minimum inventory value must be positive")
int MinInv;
@Min(value = 0, message = "max inventory value must be positive")
int MaxInv;

**line 98-113: creation of 4 new getters and setters for MinInv and MaxInv validators**


    public int getMinInv() {
        return MinInv;
    }

    public void setMinInv(int minInv) {
        this.MinInv = minInv;
    }

    public int getMaxInv() {
        return MaxInv;
    }

    public void setMaxInv(int maxInv) {
        this.MaxInv = maxInv;
    }

**filename: mainscreen.html**

**line 53-54: added table headers for PC Parts to display min and max inventory value**

<th>Min Inventory</th>
<th>Max Inventory</th>

**line 63-64: added table rows for min and max inv**

<td th:text="${tempPart.MinInv}">1</td>
<td th:text="${tempPart.MaxInv}">1</td>

**filename: BootStrapData.java**

**line 50-51, 61-62, 76-77, 88-89, 100-101: set the min and max values for each "variable" for 2 inhouseparts 
and 3 outsourced parts**

"variable".setMinInv(1);
"variable".setMaxInv(50);

**filename: InhousePartForm.html**

**line 26-37: added inhouse parts fields for entering min and max inventory to the html file and shows validation error message
in bulleted list when the submit button is pressed.**

<p><input type="text" path="minInv" th:field="*{minInv}" placeholder="Minimum Inventory" class="form-control mb-4 col-4"/></p>
    <p th:if="${#fields.hasErrors('minInv')}" th:errors="*{minInv}">Minimum Inventory Error</p>

    <p><input type="text" path="maxInv" th:field="*{maxInv}" placeholder="Maximum Inventory" class="form-control mb-4 col-4"/></p>
    <p th:if="${#fields.hasErrors('maxInv')}" th:errors="*{maxInv}">Maximum Inventory Error</p>

    <div th:if="${#fields.hasAnyErrors()}">
        <ul>
            <li th:each="err : ${#fields.allErrors()}" th:text="${err}"></li>
        </ul>
    </div>

**filename: InventoryValidator.java**

**line 1-53: creation of a validator to check if inv <= maxInv and inv>= minInv, error message is displayed
if the validation fails**

package com.example.demo.validators;

import com.example.demo.domain.Part;
import com.example.demo.domain.Product;
import com.example.demo.service.ProductService;
import com.example.demo.service.ProductServiceImpl;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.ApplicationContext;

import javax.validation.ConstraintValidator;
import javax.validation.ConstraintValidatorContext;

/**
*
*
*
*
*/
public class InventoryValidator implements ConstraintValidator<ValidInventory, Part> {
@Autowired
private ApplicationContext context;
public static ApplicationContext myContext;

    @Override
    public void initialize(ValidInventory constraintAnnotation) {
        //ConstraintValidator.super.initialize(constraintAnnotation);
    }

    @Override
    public boolean isValid(Part part, ConstraintValidatorContext constraintValidatorContext) {
        //create code to check if inventory is between min and max
        if (part.getInv() > part.getMaxInv()) {

            //display error message when inventory is greater than max inventory
            constraintValidatorContext.buildConstraintViolationWithTemplate("Solution fix your inventory it is greater than the max inventory").addConstraintViolation();

            return false;
        }
        //create code to check if inventory is between min and max
        if (part.getInv() < part.getMinInv()) {

            //display error message when inventory is less than min inventory
            constraintValidatorContext.buildConstraintViolationWithTemplate("Solution fix your inventory it is less than the min inventory").addConstraintViolation();

            return false;
        }

        return true;
    }
}

**filename: ValidInventory.java**

**line 1-25: created annotation of the validator to check that inventory is between min and max, if not the page displays
an error message "Inventory Error"**

package com.example.demo.validators;

import javax.validation.Constraint;
import javax.validation.Payload;
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

/**
*
*
*
*
*/
@Constraint(validatedBy = {InventoryValidator.class})
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
public @interface ValidInventory {
String message() default "Inventory Error!";
Class<?> [] groups() default {};
Class<? extends Payload> [] payload() default {};

}

**filename: OutsourcedPartForm.html** 

**line 25-36: added outsourced parts fields for entering min and max inventory to the html file and shows validation error message
in bulleted list when the submit button is pressed.**

    <p><input type="text" path="minInv" th:field="*{minInv}" placeholder="Minimum Inventory" class="form-control mb-4 col-4"/></p>
    <p th:if="${#fields.hasErrors('minInv')}" th:errors="*{minInv}">Minimum Inventory Error</p>

    <p><input type="text" path="maxInv" th:field="*{maxInv}" placeholder="Maximum Inventory" class="form-control mb-4 col-4"/></p>
    <p th:if="${#fields.hasErrors('maxInv')}" th:errors="*{maxInv}">Maximum Inventory Error</p>

    <div th:if="${#fields.hasAnyErrors()}">
        <ul>
            <li th:each="err : ${#fields.allErrors()}" th:text="${err}"></li>
        </ul>
    </div>

**H.  Add validation for between or at the maximum and minimum fields. The validation must include the following:
•  Display error messages for low inventory when adding and updating parts if the inventory is less than the minimum number of parts.
•  Display error messages for low inventory when adding and updating products lowers the part inventory below the minimum.
•  Display error messages when adding and updating parts if the inventory is greater than the maximum.**

**filename: MinimumValidator.java**

**line 1-24: Created new validator with message to display part inventory fallen below the set minimum**

package com.example.demo.validators;

import javax.validation.Constraint;
import javax.validation.Payload;
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

/**
*
*
*
*
*/
@Constraint(validatedBy = {MinValid.class})
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
public @interface MinimumValidator {
String message() default "Part inventory fallen below the set minimum!";
Class<?> [] groups() default {};
Class<? extends Payload> [] payload() default {};

}

**filename: MinValid.java**

**line 1-30: created file for validator, checks if inventory is greater than the minimum and if inventory is equal to
or below the minimum.**

package com.example.demo.validators;

import com.example.demo.domain.Part;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.ApplicationContext;

import javax.validation.ConstraintValidator;
import javax.validation.ConstraintValidatorContext;

/**
*
*
*
*
*/
public class MinValid implements ConstraintValidator<MinimumValidator, Part> {
@Autowired
private ApplicationContext context;
public static ApplicationContext myContext;

    @Override
    public void initialize(MinimumValidator constraintAnnotation) {
        //ConstraintValidator.super.initialize(constraintAnnotation);
    }

    @Override
    public boolean isValid(Part part, ConstraintValidatorContext constraintValidatorContext) {
        return part.getInv() > part.getMinInv();
    }
}

**filename: MaximumValidator.java**

**line 1-24: Created new validator with message to display part inventory is over stocked above the set maximum**

package com.example.demo.validators;

import javax.validation.Constraint;
import javax.validation.Payload;
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

/**
*
*
*
*
*/
@Constraint(validatedBy = {MaxValid.class})
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
public @interface MaximumValidator {
String message() default "Part inventory is over stocked above the set maximum!";
Class<?> [] groups() default {};
Class<? extends Payload> [] payload() default {};

}

**filename: MaxValid.java**

**line 1-30: created file for validator, prevents a part from having more items in inventory that the maximum set value**

package com.example.demo.validators;

import com.example.demo.domain.Part;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.ApplicationContext;

import javax.validation.ConstraintValidator;
import javax.validation.ConstraintValidatorContext;

/**
*
*
*
*
*/
public class MaxValid implements ConstraintValidator<MaximumValidator, Part> {
@Autowired
private ApplicationContext context;
public static ApplicationContext myContext;

    @Override
    public void initialize(MaximumValidator constraintAnnotation) {
        //ConstraintValidator.super.initialize(constraintAnnotation);
    }

    @Override
    public boolean isValid(Part part, ConstraintValidatorContext constraintValidatorContext) {
        return part.getInv() <= part.getMaxInv();
    }
}


**filename: Part.java**

**line 26-26: added custom validation annotations for the recent created validators**

@MinimumValidator
@MaximumValidator

**filename: EnufPartsValidator.java**

**line 36-50: added and if statements to check the values for remaining parts in the inventory when purchasing products
and added error messages to display when the conditions are met.**

            if (p.getInv() < product.getInv() - myProduct.getInv()) {
                constraintValidatorContext.disableDefaultConstraintViolation();
                constraintValidatorContext.buildConstraintViolationWithTemplate("Inventory level too low for part: " + p.getName()).addConstraintViolation();
                return false;
                }
                if (p.getInv() < product.getInv() - myProduct.getInv() + p.getMinInv()) {
                    constraintValidatorContext.disableDefaultConstraintViolation();
                    constraintValidatorContext.buildConstraintViolationWithTemplate("Adding these product will lower the part below its minimum value: " + p.getName()).addConstraintViolation();
                    return false;
                }
            }
            return true;
        }
                return true;
            }
    }

**I.  Add at least two unit tests for the maximum and minimum fields to the PartTest class in the test package.**

**filename: PartTest.java**

**line 159-199: unit tests to check that the parts class getters and setters for minimum inventory and maximum inventory**



    @Test
    void getMinInv() {
        int MinInv = 1;
        partIn.setMinInv(MinInv);
        assertEquals(MinInv, partIn.getMinInv());
        partOut.setMinInv(MinInv);
        assertEquals(MinInv, partOut.getMinInv());
    }

    @Test
    void setMinInv() {
        int MinInv = 1;
        partIn.setMinInv(MinInv);
        assertEquals(MinInv, partIn.getMinInv());
        partOut.setMinInv(MinInv);
        assertEquals(MinInv, partOut.getMinInv());
    }

    @Test
    void getMaxInv() {
        int MaxInv = 50;
        partIn.setMaxInv(MaxInv);
        assertEquals(MaxInv, partIn.getMaxInv());
        partOut.setMaxInv(MaxInv);
        assertEquals(MaxInv, partOut.getMaxInv());
    }

    @Test
    void setMaxInv() {
        int MaxInv = 50;
        partIn.setMaxInv(MaxInv);
        assertEquals(MaxInv, partIn.getMaxInv());
        partOut.setMaxInv(MaxInv);
        assertEquals(MaxInv, partOut.getMaxInv());
    }


    }

**J.  Remove the class files for any unused validators in order to clean your code.**

**filename: ValidDeletePart.java**
**filename: DeletePartValidator.java**

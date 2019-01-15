# php-standards
Extensive research on PHP standards across different ways and platforms


# PSR Standards

Coding PHP should use and follow PSR standards at [php-fig](https://www.php-fig.org), regardless of PHP versions

-   [PSR-1](https://www.php-fig.org/psr/psr-1/): Basic Coding Standard (Namespace not included)
-   [PSR-2](https://www.php-fig.org/psr/psr-2/): Coding Style Guide

  

# Naming Conventions

In addition to [PSR-1](https://www.php-fig.org/psr/psr-1/) naming convention stated, we should do it like this:

## Class

First letter capital, camel case and easy to read and understand. Should also relates to what should the class be doing and the name of the class and name of the file should be exactly the same.

ex: UserModel.php

## Others

First letter small caps, camel case and easy to read and understand. Should also relates to what it does

ex: autoExportReportView.php

  

# Prefixes and Suffixes for Classes

You should add appropriate prefixes and suffixes for the classes.

If the class if for showing content like views, add Views as a suffix: homePageView.php

If the class is a controller: HomePageController.php

if the class is a model: HomePageModel.php

and etc.

  

# The Order of Properties/Methods in a Class

In a class, properties are defined first, and then the methods.

For the order of properties and methods, public methods come first, then protected, and finally private.

Among the methods, constructors (__construct()).

The order should follow alphabetically in order, as possible.

Class methods should be declared either public or private.


    class MyClass
    {
    
        public $property1;
    
        protected $property2;
    
        private $property3;
    
        public function __construct()
        {
            // code here
        }
    
        public function myPublicFunction()
        {
            // code here
        }
    
        private function myPrivateFunction()
        {
            // code here
        }
    
    }

  

# Indention and spaces

As [PSR-2](https://www.php-fig.org/psr/psr-2/) dictates that indention should be 4 (four blank spaces).

And every child node should be indented once from parent.

    public function myFunction(array $results = array()) // parent
    {
    
    	$return = array(); // child/sibling
    
    	foreach ($results as $k => $v) { // child/sibling/parent
    		$return[] = $v; // child
    	}
    
    	return $return; // child/sibling
    }

  

# Inline PHP

## HTML

If the modified code is in between HTML tags:

    <select class="form-group <?php echo $hide ? 'hide' : ''; ?>">
    	<option value="">Select Value</option>
    	<?php foreach ($results as $k => $v ) { ?>
    		<?php if ($v != $someValue) { ?>
    			<option value="<?php echo $v; ?>"><?php echo $v; ?></option>
    		<?php } ?>
    	<?php } ?>
    </select>


## Javascript and CSS

If the modified file is inside a Javascript or CSS block:

    <script>
    	
    	var stringVar = '<?php echo $string;?>';
    	var numberVar = <?php echo $number ? $number : 0; ?>;
    
    </script>
    
      
    
    <style>
    
    	.form-inline {
    		padding: <?php echo $padding; ?>px;
    	}
    
    </style>

  

# Arrays

Put a Comma after the Last Element of Arrays Taking Multiple Lines.

This is because it is easier to read the differences when adding elements.

The following two styles of writing arrays result in the same values. However, the first style is recommended.

    // recommended style
    $array = [
        'value1',
        'value2',
        'value3', // comma at the end of last line
    ];
    
    // not recommended
    $array = [
        'value1',
        'value2',
        'value3'  // no comma at the last line
    ];

  

# Function or Method Arguments/Parameters

You should write 3 or more arguments on a new line.

It's a lot easier to manage and put comments on each parameters.

Always make sure to add the type and default value if possible before the parameter.

    function myFunction(
    	array $array = array(),
    	$integer = 0,
    	$object = null, // this is a comment intended for $object
    	$string = ''
    ) 
    {
    	// code here
    }

_Other valid types such as string, bool, object, etc are applicable for PHP7.0 and above_

  

  
----------

References:

-   [https://www.php-fig.org/](https://www.php-fig.org/)
-   [https://blog.sideci.com/5-php-coding-standards-you-will-love-and-how-to-use-them-adf6a4855696](https://blog.sideci.com/5-php-coding-standards-you-will-love-and-how-to-use-them-adf6a4855696)

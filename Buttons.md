:checkered_flag: picoCTF{button_button_whose_got_the_button_3e5652dd}

## Solve
There is a website running at `http://2018shell.picoctf.com:7949` ([link](http://2018shell.picoctf.com:7949/)). Try to see if you can push their buttons.

## Hints
What's different about the two buttons?

## Solution
```html
<!-- view-source:http://2018shell.picoctf.com:7949/ -->
<div class="panel panel-primary" style="margin-top:50px">
    <div class="panel-heading">
        <h3 class="panel-title">BUTTON1</h3>
    </div>
    <div class="panel-body">
        <form action="button1.php" method="POST">
            <input type="submit" value="PUSH ME! I am your only hope!"/>
        </form>
    </div>
</div>
```

```html
<!-- view-source:http://2018shell.picoctf.com:7949/button1.php -->
<div>
    You did it! Try the next button: <a href="button2.php">Button2</a>
</div>
```

![1](https://raw.githubusercontent.com/shoulderhu/wordpress/master/picoCTF/2018/Web%20Exploitation/Buttons/Buttons-1.png)

![2](https://raw.githubusercontent.com/shoulderhu/wordpress/master/picoCTF/2018/Web%20Exploitation/Buttons/Buttons-2.png)

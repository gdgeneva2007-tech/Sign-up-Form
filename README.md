# Sign-up-Form

# How to import fonts and use them? (tailwind css pre-installed)
1. Keep the <link> tags for Google Fonts. They are perfect.

2. Open your input.css file (the one where you have @import "tailwindcss";).
In v4, you add a @theme block to define your variables. Add this code:
*****************
@import "tailwindcss";

@theme {
  /* 1. Set "DM Sans" as your default sans-serif font */
  --font-sans: "DM Sans", sans-serif;

  /* 2. Create a custom utility for the "Knewave" font */
  /* This creates the class: font-odin */
  --font-odin: "Knewave", cursive;
}
*****************

3. That's it! 
Now you can use the classed immediately in your HTML:
********************
<body>
  <div class="overflow-hidden h-screen w-screen flex">
    
    <!-- Left Side -->
    <div class="relative w-1/3 h-full bg-[url('./background.png')] bg-left bg-cover bg-no-repeat">
      <div class="absolute top-50 w-full h-30 bg-black/50">
        <div class="flex gap-3 justify-center">
             <!-- Use your custom font variable name here -->
             <h1 class="font-odin text-6xl text-white">ODIN</h1>
        </div>
      </div>
    </div>

    <!-- Right Side -->
    <div class="flex-1 p-10">
      <!-- Since we set --font-sans to DM Sans, this text 
           automatically uses it without adding a class! -->
      <p>This text is automatically DM Sans.</p>
    </div>

  </div>
</body>
****************

1. When you write this in your CSS:
--font-sans: "DM Sans",sans-serif;
You are telling Tailwind: Replace your default standard font with this font.
Tailwind automatically applies the style of --font-sans to your entire HTML 'body'

2. The 'link' tags: CRITICAL
The CSS Class: USELESS
The only thing you need from that CSS snippet is the NAME

# Other notes:
1. self-start prevents flex elements from growing in the Cross Axis
2. class="relative w-1/3 h-full bg-[url('........')] bg-left bg-cover bg-no-repeat"
3. Remove the input boxes' browser default outline: outline-none      
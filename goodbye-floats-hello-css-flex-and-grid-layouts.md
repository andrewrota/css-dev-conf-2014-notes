# Goodbye, Floats! Hello, CSS Flex & Grid Layouts!
**#goodbyefloats; by Kenzey B. Conrad, [@WebQ2](http://twitter.com/WebQ2)** 

**What is a Float?**

An element should be taken from the normal flow and placed along the left or right side of its container.  Once you start adding more than one you have to clear floats.  Floats don't give you nice clean code.  Float has solved many, many layout problems, including using tables for layouts.

**Layout modes**

Current layout methods are block, inline, table, and positioning.

Now we have...

##Flex Layouts

Designed for more complex applications and web pages.  Standards aren't giving us redundant tools, they're giving us things that give us new features.

Flex layouts are not capable of complex text or data.  Flex has its place, just like floats have their place.

> The main idea behind flex layout is to give the container the ability to alter its items' width, height, and order to best fill the available space... - Chris Coyier

This allows us to distribute space and align content.

Support: IE11+ and almost everything else.  If you're dealing with IE8/IE9 then you're going to have some issues.

`display: flex`, then control page element with direction, alignment, and spacing.

Add flexibility to your design: layout content into columns and rows and in any direction.

**Top Aligned:**

    display: flex
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-start
    
`display: flex` causes an element to generate a block-level flex container box.  Flex containers are not block containers.  Floats and clear have no effect on a flex item.  `vertical-align` has no effect.  You won't need it.

`flex-wrap` allos us to wrap multiple lines.  `nowrap` is the initial value.  Check the initial values.  

`justify-content: space-between` will distrubte items on the line from the starting point to the ending point evenly.

**Middle Aligned**

    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    
**Bottom Aligned**

    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-end;
    
**Display Order Can Be Reversed**

    flex-direction: row-reverse
    
**Centering**

    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: center;
    
**Wrapping of Long Lines**

    display: flex;
    flex-direction: row;
    flex-wrap: row;
    align-items: center;
    justify-content: center;
    align-content: flex-end;

Wrapped items end up in the middle of the second row.

No effect when there is only one line.

## Grid Layouts

It's a ways off, but it's coming.  It will be an important tool once it arrives in browsers.  

Layout content in columns and rows.  Grids don't have content structure.

Enables layouts not possible with tables.

Easily adapt layouts for different devices.

You'll be able to name lines and specify what happens at each one.


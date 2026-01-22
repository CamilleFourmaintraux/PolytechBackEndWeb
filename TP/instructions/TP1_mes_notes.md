# Prise de notes pour le TP1


## EXO Mise en pratique

```
/**
 * You can edit, run, and share this code.
 * play.kotlinlang.org
 */

interface  Quadrilateral {
    fun getPerimeter(): Double
    fun getArea(): Double
}

class Trapezium(val longSide: Double, val shortSide: Double, val height: Double): Quadrilateral {
    override fun getPerimeter(): Double {
        return 2*height + shortSide + longSide
    }
    override fun getArea(): Double {
        return height * ((shortSide + longSide)/2)
    }
}

class Rectangle(val height: Double, val width: Double): Quadrilateral {
    override fun getPerimeter(): Double {
        return 2*height + 2*width
    }
    
    override fun getArea(): Double {
        return height * width
    }
}

class Square(val size: Double): Quadrilateral {
    override fun getPerimeter(): Double {
        return 2*size
    }
    
    override fun getArea(): Double {
        return size*size
    }
}

fun main() {
    println("Hello, world!!!")
}
```


## EXO Bonus de Mise en pratique

```
/**
 * Adding some more fun because why not
 * 
 * */

interface Quadrilateral {
    fun getPerimeter(): Double
    fun getArea(): Double
    fun drawShape() {
        println(
        """
        ---
       /  |
      /   |
      \   |
       \  |
        \ |
         \|
        """)
    }
}

class Trapezium(val longSide: Double, val shortSide: Double, val height: Double = 12.0) : Quadrilateral {
    override fun getPerimeter(): Double {
        val side = Math.sqrt(((longSide - shortSide) / 2) * ((longSide - shortSide) / 2) + height * height)
        return longSide + shortSide + 2 * side
    }

    override fun getArea(): Double {
        return (longSide + shortSide) * height / 2
    }
}

class Rectangle(val height: Double, val width: Double): Quadrilateral {
    override fun getPerimeter(): Double {
        return 2 * height + 2 * width
    }

    override fun getArea(): Double {
        return height * width
    }
    
    override fun drawShape() {
        println(
        """
        +-----+
        |     |
        +-----+
        """)
    }
}

class Square(val side: Double): Quadrilateral {
    override fun getPerimeter(): Double {
        return 4 * side
    }

    override fun getArea(): Double {
        return side * side
    }
    override fun drawShape() {
        println(
        """
        +---+
        |   |
        +---+
        """)
    }
}

fun main() {
    val s: Square = Square(2.3)
    val r: Rectangle = Rectangle(1.2, 2.3)
    val t: Trapezium = Trapezium(5.0, 3.0)
    s.drawShape()
    r.drawShape()
    t.drawShape()
}
```

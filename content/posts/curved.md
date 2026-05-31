+++
date = '2026-05-31T23:53:03+07:00'
draft = false
title = 'Curved'
+++

Cara buat curved modifier untuk card

```kotlin
class CurvedBottomShape(private val curveDepth: Dp) : Shape {
    override fun createOutline(
        size: Size,
        layoutDirection: LayoutDirection,
        density: Density
    ): Outline {
        val path = Path().apply {
            val curveDepthPx = with(density) { curveDepth.toPx() }
            moveTo(0f, 0f)
            lineTo(size.width, 0f)
            val ySide = size.height - curveDepthPx
            lineTo(size.width, ySide)
            quadraticTo(
                x1 = size.width / 2f,
                y1 = size.height + curveDepthPx,
                x2 = 0f,
                y2 = ySide
            )
            close()
        }
        return Outline.Generic(path)
    }
}
```

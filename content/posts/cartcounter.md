+++
date = '2026-06-07T00:07:13+07:00'
draft = false
title = 'Cartcounter'
tags = ["JetpackCompose"]
+++

```kotlin
@Composable
fun AddPlusMinusButton() {
    val primaryOrange = Color(0xFFED954D)
    val lightPeach = Color(0xFFFAF0E7)
    val lightCream = Color(0xFFFFF6EE)
    val darkGray = Color(0xFF2C2C2C)
    val textGray = Color(0xFF8C8C8C)
    val dividerColor = Color(0xFFEFEFEF)

    Scaffold() { paddingValues ->
        Box(
            modifier = Modifier.fillMaxSize()
        ) {
            Row(
                modifier = Modifier
                    .clip(RoundedCornerShape(8.dp))
                    .background(lightCream)
                    .padding(horizontal = 4.dp, vertical = 2.dp)
                    .align(
                        Alignment.Center
                    ),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.Center
            ) {
                // Minus Button
                Box(
                    modifier = Modifier
                        .size(28.dp)
                        .clickable { },
                    contentAlignment = Alignment.Center
                ) {
                    Text(
                        text = "–",
                        fontSize = 16.sp,
                        fontWeight = FontWeight.Medium,
                        color = darkGray
                    )
                }

                // Quantity Value
                Text(
                    text = "$2",
                    fontSize = 15.sp,
                    fontWeight = FontWeight.Medium,
                    color = darkGray,
                    modifier = Modifier.padding(horizontal = 8.dp)
                )

                // Plus Button
                Box(
                    modifier = Modifier
                        .size(28.dp)
                        .clickable { },
                    contentAlignment = Alignment.Center
                ) {
                    Text(
                        text = "+",
                        fontSize = 16.sp,
                        fontWeight = FontWeight.Medium,
                        color = darkGray
                    )
                }
            }
        }
    }
}

```

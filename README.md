Este proyecto se llevará a cabo con un dataset sobre las canciones más escuchadas hasta el año 2024 en plataformas como Spotify (S), YouTube (Y) y TikTok (T). Cuenta con 29 columnas entre las que destaco:
"Track"; "Album Name"; "Artist"; "Release Date"; "Spotify Streams"; "YouTube Views"; "TikTok Views"; y "Explicit Track".

La primera modificación que llevé a cabo fue convertir "Release Date" a formato fecha. A continuación, definí a "All Time Rank" como el índice del dataset.

Los dos primeros gráficos son gráficos de barras con matplotlib y bokeh para visualizar los 8 artistas con mayor cantidad de reproducciones, liderando Drake y Taylor Swift.

Para hacer un análisis de las reproducciones en Spotify, YouTube y TikTok los transformé de object a int64, y posteriormente creé columnas en millones: "Spotify_MM_Streams", "YouTube_MM_Views" y "TikTok_MM_Views". Por último, creé el df "top_10_streams_df_unique" para quedarme con las top 10 canciones de Spotify, y dentro de ese ranking, las reproducciones de YouTube y TikTok.
Dado esto, generé un gráfico de dispersión con Bokeh. Las variables bajo estudio fueron "Spotify_MM_Streams" (eje X) y "YouTube_MM_Views" (eje Y), se puede apreciar que canciones como Blinding Lights de The Weekend están en el top 1 de Spotify pero en un ranking relativamente bajo en YouTube. Caso contrario con Believer de Imagine Dragons.

Siguiendo con la comparación entre S y Y, grafiqué un line_plot con las reproducciones de cada plataforma entre los años 2000 y 2024. Hasta el 2016 tienen rendimientos positivos casi similares.
En 2017, YouTube comienza a decrecer; y en 2019, lo mismo para Spotify pero en menor medida.

PRUEBA DE HIPÓTESIS
¿Son las reproducciones de las canciones en Spotify con contenido explícito (1) significativamente diferentes de las que no tienen este contenido (0)?

μ1 = μ de reproducciones en Spotify de canciones con contenido explícito
μ2 = μ de reproducciones en Spotify de canciones sin contenido explícito

H0: μ1 = μ2
H1: μ1 ≠ μ2

Habiendo realizado el Test-T e Intervalos de Confianza para la prueba de hipótesis, concluyo que no hay evidencia suficiente (o dicho de otro modo, no existe una diferencia estadísticamente significativa en el número promedio de transmisiones de Spotify entre canciones explícitas y no explícitas*) para rechazar H0.
Aunque puede haber alguna diferencia en las transmisiones promedio observadas entre los dos tipos de canciones en su muestra, esta diferencia no es lo suficientemente grande como para concluir con seguridad que existe una diferencia real en la población general de canciones.

IDENTIFICACIÓN DE OUTLIERS
Procedí a generar un Z Score con Matplotlib y Bokeh para ver las reproducciones atípicas en Spotify en el 2023. Con esos gráficos, surgió la curiosidad si las reproducciones se debían a artistas reconocidos y por eso los valores tan altos.
Para ello, relacioné las reproducciones atípicas, previamente identificadas, con el top 100 de artistas.
Pude concluir que de los 32 outliers, 18 (el 56%) se deben a que fueron promovidos por artistas extremadamente famosos y talentosos como ser Miley Cyrus, Bizarrap, Dua Lipa, etc.


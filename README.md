# PruebaTecnicaNetCore
prueba tecnica net core 
ESTRUCTURA DEL PROYECTO.

1. CONTROLADORES.
   CategoriasController.cs
   AutoresController.cs
   LibrosController.cs
2. MODELOS
   Libro.cs
   Autor.cs
   Categoria.cs
3. MENAJO DE BASE DE DATOS 
   ApplicationDbContext.cs 
   aplicando EntityFramework   haciendo la conexion con una base de datos.
   esto se refleja en el Startup, se habilito el servicio 
   
    services.AddDbContext<Models.ApplicationDbContext>
                (options => options.UseSqlServer(Configuration.GetConnectionString("defaultConnection")));
   
   
4. SEGURRIDAD 
   Se aplico en el controlador    "LibrosController"   un (Json Web  Tokens )
   
   esto se  refleja en la cabecera de la clase  por medio del atributo :   
   [Authorize(AuthenticationSchemes =JwtBearerDefaults.AuthenticationScheme)]  

  y en el archivo "Startup" se  inicializo por medio del sevicio 
  
            services.AddMvc().AddJsonOptions(ConfigureJson);  // Servicio para el manejo de Json 
            
            services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)  // Servicio para el manejo de los Json token
                .AddJwtBearer();
  
   

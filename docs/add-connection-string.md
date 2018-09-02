1.open file appsettings.json
2.add follow 
    {   
        .... 
        "ConnectionStrings":{
            "DefaultConnection":"Data Source=DatingApp.db"
        }
        .....
    }
3. open file Startup.cs 
    public void ConfigureServices(IServiceCollection services)
    {

            /**
            add database context 
            */
            services.AddDbContext<DataContext>( 
                x => x.UseSqlite(Configuration.GetConnectionString("DefaultConnection")));

            ...
    }

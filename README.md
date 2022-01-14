# DOAN PHUC KHOA S3927381
<html>
    <head>
        <title>Headlines</title>
        <style>
          html{
            font-family: "Helvetica";
            background: white;
          }

          body{
            background: lightgrey;
            max-width: 900px;
            margin: 0 auto;
          }

          #header{
            padding-top: 5;
            background: lightsteelblue;
          }
          #inner-header {
            padding-left: 10;
          }
          #main{
            padding-left: 10;
          }
        </style>
    </head>
    <body>
      <div id="header">
        <div id="inner-header">
        <h1>Headlines</h1>
        <p>Headlines. Currency. Weather</p>
      </div>
        <hr />
      </div>
      <div id="main">  
        <h2>Current weather</h2>

        <form>
          <input type="text" name="city" placeholder="weather search">
          <input type="submit" value="Submit">
        </form>

        <p>City: <b>{{weather.city}}, {{weather.country}}</b></p>
        <p>{{weather.description}} |{{weather.temperature}}&#8451</p>

        <h2>Currency</h2>

        <form>
            from: <select name="currency_from">
                    {% for currency in currencies %}
                        <option value="{{currency}}" {{'selected="selected"' if currency_from==currency}}>{{currency}}</option>
                    {% endfor %}
                  </select>

             to: <select name="currency_to">
                    {% for currency in currencies %}
                        <option value="{{currency}}" {{'selected="selected"' if currency_to==currency}}>{{currency}}</option>
                    {% endfor %}
                  </select>
                 <input type="submit" value="Submit">
        </form>

        1 {{currency_from}} = {{currency_to}} {{rate}}

        <h2>Headlines</h2>
        <form>
          <input type="text" name="query" placeholder="search" />
          <input type="submit" value="Submit" />
        </form>

        {% for article in articles %}
            <b><a href="{{article.link}}">{{article.title}}</a></b><br />
            <i>{{article.published}}</i><br />
            <p>{{article.summary}}</p> 
            <hr />
        {% endfor %}
     </div>
    </body>
</html>


# 🌦️ GraphQL Weather API
#### A GraphQL Wrapper for the [Open Weather Map API](https://openweathermap.org/api)

Retrieve the current weather for any given city. Since this GraphQL API uses the free-tier of the Open Weather Map API, it is restricted to 60 calls/minute. 

However, feel free to use it for prototyping and demo projects anyways. A live version is available at:

[graphql-weather-api.herokuapp.com](https://graphql-weather-api.herokuapp.com/) 🌈

## How to Use

#### Queries

* getCityByName (`name` *required*, `country` *optional*, `config` *optional*)
* getCityById (`id` *required*, , `config` *optional*)

*Language and unit system can be specified via `config`.*

#### Example with all weather data

```graphql
query {
  getCityByName(name: "Gothenburg") {
    id
    name
    country
    coord {
      lon
      lat
    }
    weather {
      summary {
        title
        description
        icon
      }
      temperature {
        actual
        feelsLike
        min
        max
      }
      wind {
        speed
        deg
      }
      clouds {
        all
        visibility
        humidity
      }
      timestamp
    }
  }
}
```

## How to Install

For running this project locally, you must register your own application at [Open Weather Map](https://openweathermap.org/api). Then, create an .env file and add the following variable: `KEY=<YOUR-APP-ID>`

```sh
npm install
npm run dev # Using nodemon for auto-reloading
```
The server starts at http://localhost:4000/


## About

Konstantin Münster – [konstantin.digital](https://konstantin.digital) – [mail@konstantin.digital](mailto:mail@konstantin.digital)

Distributed under the [MIT](http://showalicense.com/?fullname=Konstantin+M%C3%BCnster&year=2019#license-mit) license. 
See ``LICENSE`` for more information.

[https://github.com/konstantinmuenster](https://github.com/konstantinmuenster)

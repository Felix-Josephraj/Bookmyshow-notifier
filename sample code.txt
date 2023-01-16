// console.log('hello team')

import fetch from 'node-fetch'
import cheerio, { load } from 'cheerio'

// function to get the raw data
const getRawData = (URL) => {
  return fetch(URL)
    .then((response) => response.text())
    .then((data) => {
      return data
    })
}

// URL for data
const URL = 'http://webcode.me/'
// 'https://in.bookmyshow.com/buytickets/varisu-trichy/movie-tric-ET00332034-MT/20230113'

// start of the program
const getCricketWorldCupsList = async () => {
  // const cricketWorldCupRawData = await getRawData(URL)
  // // const body = await cricketWorldCupRawData.text()
  // const parsedCricketWorldCupData = cheerio.load(cricketWorldCupRawData)
  // // console.log(cricketWorldCupRawData)
  // // const worldCupsDataTable =
  // //   parsedCricketWorldCupData('table.wikitable')[0].children[1].children
  // let title = cheerio('title')
  // console.log(title.text())
  // console.log('title.text()')
  // // console.log(JSON.stringify(parsedCricketWorldCupData))
  // // console.log(parsedCricketWorldCupData.html)

  const url =
    // 'http://webcode.me'
    // 'https://in.bookmyshow.com/trichy/cinemas/ramba-ac-dolby-atmos-trichy/RAMB'
    'https://in.bookmyshow.com/trichy/cinemas/la-cinema-maris-complex-rgb-laser-trichy/LATG/20230114'

  const response = await fetch(url)
  const body = await response.text()

  let $ = load(body)

  // let title = $('.listing-info')
  let title = $('.nameSpan')
  console.log(title.text())
}

// invoking the main function
getCricketWorldCupsList()

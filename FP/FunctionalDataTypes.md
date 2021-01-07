***tuples (that is, an array with a fixed number of elements of (probably) different types), we
can write something like the following:
// getWeekAndDay :: String → (Number × String)
const getWeekAndDay = yyyy_mm_dd => [weekNumber, dayOfWeekName];

*** Sum types (also known as union types) are defined as a list of possible values.
// getField :: String → attr → a | undefined
const getField = attr => obj => obj[attr];
# Movie-Project
My first Git project for movies.
movies = {
 Interstellar: 5
 
}
puts "Type add to add a movie."
puts "Type update to update a movie rating."
puts "Type display to show all movies and ratings."
puts "Type delete to remove a movie."
choice = gets.chomp

case choice
when "add"
    puts "Movie title please."
title = gets.chomp
if movies[title.to_sym].nil? then puts "Rating for Movie"
    rating = gets.chomp
    movies[title.to_sym] = rating.to_i
else
    puts "Movie already exists"
end
when "update"
    puts "Title please!"
    title = gets.chomp
    if movies[title.to_sym].nil? then puts "Movie is not in hash."
    else
        puts "New movie rating please."
        rating = gets.chomp
        movies[title.to_sym] = rating.to_i
     end  
when "display"
    movies.each do |movie, rating|
        puts "#{movie}: #{rating}"
         end
when "delete"
    puts "Title you wish to remove"
    title = gets.chomp
    if movies[title.to_sym].nil? then puts "Movie is not in hash."
    else
        movies.delete(title.to_sym)
    end
else
    puts "Error!"
end

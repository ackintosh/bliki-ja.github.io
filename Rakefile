# Usage: rake page title="A Title"
desc "Create a new page."
task :page do
  title = ENV["title"] || "new-post"
  name = "#{title}.md"
  filename = File.join('.', "#{name}")
  title = File.basename(filename, File.extname(filename)).gsub(/[\W\_]/, " ").gsub(/\b\w/){$&.upcase}
  if File.exist?(filename)
    abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end

  mkdir_p File.dirname(filename)
  puts "Creating new page: #{filename}"
  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: page"
    post.puts "title: "
    post.puts 'description: ""'
    post.puts "---"
  end
end # task :page
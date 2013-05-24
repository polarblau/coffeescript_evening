site = OpenStruct.new({
  :ssh_user    => "polarbla@polarblau.com",
  :remote_root => "public_html/clients/eniram/wp-content/themes/eniram/",
  :public_url  => "http://www.polarblau.com/clients/eniram/"
})

desc "Deploy 'deploy' dir to #{site.ssh_user}:#{site.remote_root}"
task :deploy do
  Dir.chdir(".") do
    puts
    puts "Deploying: #{Dir.pwd} -> #{site.ssh_user}:#{site.remote_root}"
    puts
    system("rsync -cvr --delete --exclude-from ./deploy_excludes.txt . #{site.ssh_user}:#{site.remote_root}")
    puts
    puts "Done."
  end
end

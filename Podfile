
install! 'cocoapods', :preserve_pod_file_structure => true

def install_pods
  project_dir = File.dirname(__FILE__)
  config_file_path = File.join(project_dir, 'current_config.txt')
  
  if File.exist?(config_file_path)
    puts "File found"
    file_content = File.read(config_file_path).strip

    if file_content == 'Release'
      pod 'SampleDevpod', :git => 'git@github.com:balrajverma/SampleDevpod.git', :branch => 'main'
      
    elsif file_content == 'Debug'
      
      pod 'SampleDevpod/QA', :git => 'git@github.com:balrajverma/SampleDevpod.git', :branch => 'main'
    else
      
      puts "Unrecognized build configuration: #{file_content}"
    end
  else
    puts "Config file not found"
  end
end


target 'MultipleVarientDevpodMainApp' do
  use_frameworks!
  install_pods
end

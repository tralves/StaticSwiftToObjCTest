# Uncomment the next line to define a global platform for your project
platform :ios, '8.0'

pod 'PlayKit'

target 'StaticSwiftToObjCTest' do
  # Uncomment the next line if you're using Swift or would like to use dynamic frameworks
  # use_frameworks!

  # Pods for StaticSwiftToObjCTest

  target 'StaticSwiftToObjCTestTests' do
    inherit! :search_paths
    # Pods for testing
  end

  target 'StaticSwiftToObjCTestUITests' do
    inherit! :search_paths
    # Pods for testing
  end

end

pre_install do |installer|
  def installer.verify_no_static_framework_transitive_dependencies; end
  Pod::Installer::Xcode::TargetValidator.send(:define_method, :verify_no_static_framework_transitive_dependencies) {}
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
      target.build_configurations.each do |config|
          #config.build_settings['ALWAYS_EMBED_SWIFT_STANDARD_LIBRARIES'] = 'NO'
          if (target.name == 'PlayKit' ||
              target.name == 'PlayKitUtils' ||
              target.name == 'Log' ||
              target.name == 'PlayKitUtils' ||
              target.name == 'KalturaNetKit' ||
              target.name == 'SwiftyXMLParser')
              config.build_settings['SWIFT_VERSION'] = '4.0'
          end
      end
  end
end

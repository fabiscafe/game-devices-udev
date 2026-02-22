project('game-controller-udev-rules',
  version: '1.0',
  meson_version: '>=1.0',
  license: 'MIT'
)

udev_dir = join_paths(get_option('prefix'), 'lib', 'udev', 'rules.d')
src_dir = meson.project_source_root() / 'src'

# Get the priority prefix
udev_priority = get_option('udev_priority')

# Map src_files to option names
# form: {'source-file' : 'option-names'}
rules_map = {
  '8bitdo-gdu.rules' : '8bitdo',
  'alpha_imaging_technology_co-gdu.rules' : 'alpha_imaging_technology',
  'astro_gaming-gdu.rules' : 'astro_gaming',
  'betop-gdu.rules' : 'betop',
  'cypress_semiconductor_corp-gdu.rules' : 'cypress_semiconductor_corp',
  'google-gdu.rules' : 'google',
  'hori-gdu.rules' : 'hori',
  'htc-gdu.rules' : 'htc',
  'logitech-gdu.rules' : 'logitech',
  'mad_catz-gdu.rules' : 'mad_catz',
  'microsoft-gdu.rules' : 'microsoft',
  'nacon-gdu.rules' : 'nacon',
  'nintendo-gdu.rules' : 'nintendo',
  'nvidia-gdu.rules' : 'nvidia',
  'pdp-gdu.rules' : 'pdp',
  'personal_communication_systems_inc-gdu.rules' : 'personal_communication_systems_inc',
  'pid_codes-gdu.rules' : 'pid_codes',
  'powera-gdu.rules' : 'powera',
  'raspberry_pi_ltd-gdu.rules' : 'raspberry_pi_ltd',
  'razer-gdu.rules' : 'razer',
  'sony-gdu.rules' : 'sony',
  'uinput-dev-early-creation.rules' : 'uinput_dev_early_creation',
  'valve-gdu.rules' : 'valve',
  'vkb_sim-gdu.rules' : 'vkb_sim',
  'zeroplus_technology_corporation-gdu.rules' : 'zeroplus_technology_corporation'
}

# Iterate over udev rule files in rules_map
# For each file, check if its corresponding option is enabled
# Prefix the src_file with udev priority number (udev_priority)
# Install the file to the udev directory
# Track installed src_files in the 'installed' list
installed = []
foreach src_file, optname : rules_map
  if get_option(optname)
    src_path = src_dir / src_file
    prefixed_file = udev_priority.to_string() + '-' + src_file

    install_data(
      src_path,
      install_dir: udev_dir,
      rename: prefixed_file
    )

    installed += prefixed_file
  endif
endforeach
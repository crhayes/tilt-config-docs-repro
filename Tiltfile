config.define_string_list("to-run", args=True)
config.define_string_list("to-edit")
cfg = config.parse()
groups = {
  'consumer': ['a', 'b', 'c'],
  'enterprise': ['a', 'b', 'd'],
}
resources = []
for arg in cfg.get('to-run', []):
  if arg in groups:
    resources += groups[arg]
  else:
    # also support specifying individual services instead of groups, e.g. `tilt up a b d`
    resources.append(arg)
config.set_enabled_resources(resources)

print(cfg.get('to-run', []));
print(resources);
print(cfg.get('to-edit', []));

local_resource('a', 'echo "Hi"');
local_resource('b', 'echo "Hi"');
local_resource('c', 'echo "Hi"');
local_resource('d', 'echo "Hi"');
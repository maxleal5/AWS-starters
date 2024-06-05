## Create our bucket
```sh
aws s3 mb s3://prefixes-expl-52
```

## Create our folder
```sh
aws s3api put-object --bucket="prefixes-expl-52" --key="hello/" 
```

## create many folders
```sh
aws s3api put-object --bucket="prefixes-expl-52" --key="Lorem/ipsum/dolor/sit/amet/consectetur/adipiscing/elit/Pellentesque/sed/semper/quam/non/aliquam/augue/Curabitur/tristique/massa/sed/iaculis/tempor/Vestibulum/dapibus/libero/non/ex/ullamcorper/sit/amet/sollicitudin/augue/placerat/Maecenas/quis/neque/id/tellus/pharetra/porttitor/nec/sed/nisi/Quisque/sed/auctor/risus/sed/gravida/lectus/Nunc/ac/ornare/urna/non/feugiat/dui/Nunc/non/justo/quis/massa/vehicula/feugiat/sed/sed/elit/Class/aptent/taciti/sociosqu/ad/litora/torquent/per/conubia/nostra/per/inceptos/himenaeos/Nullam/vel/aliquet/quam/Suspendisse/ut/faucibus/nulla/In/sodales/enim/arcu/in/volutpat/metus/gravida/idCras/iaculis/venenatis/arcu/a/vulputate/dolor/venenatis/sed/Mauris/porta/felis/sed/dictum/pulvinar/Vestibulum/venenatis/ante/sed/porta/tincidunt/tellus/purus/tincidunt/lectus/rutrum/scelerisque/augue/lectus/sit/amet/elit/Praesent/blandit/ipsum/non/fringilla/vestibulum/Phasellus/finibus/elementum/tellus/blandit/varius/Nunc/sollicitudin/tellus/sed/felis/laoreet/vel/accumsan/as/ase/fj/esafa/werfas/felim/"
```

## Try and break the 1024 limit
```sh
aws s3api put-object --bucket="prefixes-expl-52" --key="Lorem/ipsum/dolor/sit/amet/consectetur/adipiscing/elit/Pellentesque/sed/semper/quam/non/aliquam/augue/Curabitur/tristique/massa/sed/iaculis/tempor/Vestibulum/dapibus/libero/non/ex/ullamcorper/sit/amet/sollicitudin/augue/placerat/Maecenas/quis/neque/id/tellus/pharetra/porttitor/nec/sed/nisi/Quisque/sed/auctor/risus/sed/gravida/lectus/Nunc/ac/ornare/urna/non/feugiat/dui/Nunc/non/justo/quis/massa/vehicula/feugiat/sed/sed/elit/Class/aptent/taciti/sociosqu/ad/litora/torquent/per/conubia/nostra/per/inceptos/himenaeos/Nullam/vel/aliquet/quam/Suspendisse/ut/faucibus/nulla/In/sodales/enim/arcu/in/volutpat/metus/gravida/idCras/iaculis/venenatis/arcu/a/vulputate/dolor/venenatis/sed/Mauris/porta/felis/sed/dictum/pulvinar/Vestibulum/venenatis/ante/sed/porta/tincidunt/tellus/purus/tincidunt/lectus/rutrum/scelerisque/augue/lectus/sit/amet/elit/Praesent/blandit/ipsum/non/fringilla/vestibulum/Phasellus/finibus/elementum/tellus/blandit/varius/Nunc/sollicitudin/tellus/sed/felis/laoreet/vel/accumsan/as/ase/fj/esafa/werfas/felim/hello.txt" --body="hello.txt"
```
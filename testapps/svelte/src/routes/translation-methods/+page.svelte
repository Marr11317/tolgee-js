<script>
  import { T, getTranslate } from '@tolgee/svelte';
  import Navbar from '../../component/Navbar.svelte';

  const t = getTranslate();
</script>

<main class="translation-methods">
  <Navbar>
    <div slot="menu-items">
      <a href="/">The example app</a>
    </div>
  </Navbar>

  <div class="tiles">
    <div>
      <h1>T component with default</h1>
      <div>
        <T keyName="this_key_does_not_exist" defaultValue="This is default" />
      </div>
    </div>

    <div>
      <h1>T component without default</h1>
      <div>
        <T keyName="this_is_a_key" />
      </div>
    </div>
    <div>
      <h1>T component with params</h1>
      <div>
        <T keyName="this_is_a_key_with_params" parameters={{ key: 'value', key2: 'value2' }} />
      </div>
    </div>

    <div>
      <h1>T component with noWrap</h1>
      <div>
        <T
          keyName="this_is_a_key_with_params"
          parameters={{ key: 'value', key2: 'value2' }}
          noWrap={true}
        />
      </div>
    </div>

    <div>
      <h1>t function without default</h1>
      <div>
        {$t('this_is_a_key')}
      </div>
    </div>

    <div>
      <h1>t function with params</h1>
      <div>
        {$t('this_is_a_key_with_params', { key: 'value', key2: 'value2' })}
      </div>
    </div>

    <div>
      <h1>t function with noWrap</h1>
      <div>
        {$t('this_is_a_key', undefined, true)}
      </div>
    </div>

    <div>
      <h1>t function with default</h1>
      <div>
        {$t('this_key_does_not_exist', 'This is default')}
      </div>
    </div>

    <div>
      <h1>t function with props object</h1>
      <div>
        {$t('this_is_a_key', { key: 'value', key2: 'value2' })}
      </div>
    </div>

    <div>
      <h1>t function with props object noWrap is true</h1>
      <div>
        {$t({ key: 'this_is_a_key', parameters: { key: 'value', key2: 'value2' }, noWrap: true })}
      </div>
    </div>
  </div>
</main>
